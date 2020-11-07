<script>
export const BASE_BUTTON_TYPE = 'button'
export const LINK_BUTTON_TYPE = 'link'
export const NUXT_BUTTON_TYPE = 'nuxt-link'

const TYPE_TAG = {
  [BASE_BUTTON_TYPE]: 'button',
  [LINK_BUTTON_TYPE]: 'a',
  [NUXT_BUTTON_TYPE]: 'nuxt-link',
}

const BASE_BUTTON_VARIANT = 'default'
const PRIMARY_BUTTON_VARIANT = 'primary'

export default {
  name: 'CButton',
  props: {
    variant: {
      type: String,
      validator: (variant) =>
        [BASE_BUTTON_VARIANT, PRIMARY_BUTTON_VARIANT].includes(variant),
      default: BASE_BUTTON_VARIANT,
    },
    type: {
      type: String,
      default: BASE_BUTTON_TYPE,
      validator: (type) =>
        [BASE_BUTTON_TYPE, LINK_BUTTON_TYPE, NUXT_BUTTON_TYPE].includes(type),
    },
    to: {
      type: Object,
      default: () => ({}),
    },
    src: {
      type: String,
      default: '',
    },
    alt: {
      type: String,
      default: '',
    },
    target: {
      type: String,
      default: '',
    },
  },
  methods: {
    prepareBaseButtonConfig(config) {
      return Object.assign(config, {
        on: {
          click: (event) => this.$emit('click', event),
        },
      })
    },
    prepareLinkButtonConfig(config) {
      const { src, alt, target } = this
      return Object.assign(config, {
        attrs: {
          src,
          alt,
          target,
        },
      })
    },
    prepareNuxtButtonConfig(config) {
      const { to } = this
      return Object.assign(config, {
        props: { to },
      })
    },
  },
  render(h) {
    const {
      type,
      variant,
      prepareBaseButtonConfig,
      prepareLinkButtonConfig,
      prepareNuxtButtonConfig,
    } = this

    // Get tag by button type
    const tag = TYPE_TAG[type]
    let config = {
      class: ['c-button', variant ? `c-button--${variant}` : ''],
    }

    // Prepare config for vnode
    if (type === BASE_BUTTON_TYPE) config = prepareBaseButtonConfig(config)
    if (type === LINK_BUTTON_TYPE) config = prepareLinkButtonConfig(config)
    if (type === NUXT_BUTTON_TYPE) config = prepareNuxtButtonConfig(config)

    // Render prepared vnode
    return h(tag, config, this.$slots.default)
  },
}
</script>

<style lang="scss" src="./CButton.scss" />
