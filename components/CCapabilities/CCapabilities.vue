<template>
  <section class="container capabilities u-margin-xy--xxl">
    <header class="capabilities-header">
      <h2 class="capabilities-header__title title--xl">Our capabilities</h2>
      <p class="capabilities-header__text">
        Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
        nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat.
      </p>

      <CButton type="nuxt-link" variant="primary" :to="{ path: '/services' }"
        >All Services
      </CButton>
    </header>

    <ul class="row capabilities__list capabilities-list">
      <li class="capabilities-list__item capabilitie capabilitie--first">
        <h4 class="capabilitie__title title--md">
          PROJECT AND CONSTRUCTION MANAGEMENT
        </h4>
        <p class="capabilitie__desc text--nl">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
          nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat.
        </p>
      </li>

      <li class="capabilities-list__item capabilitie capabilitie--second">
        <h4 class="capabilitie__title title--md">
          STRUCTURE AUDIT AND MAINTENANCE
        </h4>
        <p class="capabilitie__desc text--nl">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
          nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat.
        </p>
      </li>

      <li class="capabilities-list__item capabilitie capabilitie--third">
        <h4 class="capabilitie__title title--md">
          FACTORY CONSTRUCTION AND MODELING
        </h4>
        <p class="capabilitie__desc text--nl">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
          nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat.
        </p>
      </li>
    </ul>
  </section>
</template>
<style lang="scss" src="./CCapabilities.scss" />
