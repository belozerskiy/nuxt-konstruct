<script>
export default {
  name: 'CVisible',
  props: {
    baseClass: {
      type: String,
      required: true,
    },
    activeClass: {
      type: String,
      required: true,
    },
    once: {
      type: Boolean,
      default: false,
    },
    throttle: {
      type: Number,
      default: 200,
    },
    reverse: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      isVisible: false,
    }
  },
  methods: {
    visibilityChanged(isVisible) {
      this.isVisible = isVisible
    },
  },
  render(h) {
    const { baseClass, activeClass, once, isVisible, reverse, throttle } = this

    return h(
      'div',
      {
        class: [
          [reverse ? activeClass : baseClass],
          {
            [reverse ? baseClass : activeClass]: isVisible,
          },
        ],
        directives: [
          {
            name: 'observe-visibility',
            value: { callback: this.visibilityChanged, once, throttle },
          },
        ],
      },
      this.$slots.default
    )
  },
}
</script>
