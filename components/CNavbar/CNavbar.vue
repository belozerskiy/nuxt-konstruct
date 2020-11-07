<template>
  <div id="c-navbar" class="c-navbar">
    <div class="container c-navbar__container">
      <nuxt-link class="c-navbar__logo" to="/">
        <img src="~assets/images/navbart-logo-black.svg" alt="Navbar Logo" />
      </nuxt-link>
      <nav class="c-navbar__nav">
        <nuxt-link
          v-for="{ title, to } in links"
          :key="title"
          :to="to"
          class="c-navbar__link"
        >
          {{ title }}
        </nuxt-link>
      </nav>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CNavbar',
  data: () => ({
    links: [
      { title: 'Home', to: { path: '/' } },
      { title: 'About', to: { path: '/about' } },
      { title: 'Services', to: { path: '/services' } },
      { title: 'Work', to: { path: '/work' } },
      { title: 'Contact', to: { path: '/contact' } },
    ],
  }),
}
</script>
<style lang="scss" src="./CNavbar.scss" />
