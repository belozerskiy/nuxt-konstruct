<template>
  <header class="c-header c-header--background">
    <nuxt-link to="/" class="c-header__logo">
      <img
        class="c-header__img"
        src="~assets/images/header-logo.svg"
        alt="Logo"
      />
    </nuxt-link>
    <div class="c-header__text">
      <h1 class="c-header__title title--xxl">Partner with konstruct</h1>
      <span class="c-header__subtitle"
        >An award-winning construction management firm</span
      >
    </div>
    <a class="c-header__scroll-button" href="#c-navbar"> Scroll Down </a>
  </header>
</template>
<script>
export default {
  name: 'CHeader',
  methods: {
    handleScrollDown() {
      const windowHeight = window.innerHeight
      scroll(0, windowHeight)
    },
  },
}
</script>
<style lang="scss" src="./CHeader.scss" scoped />
