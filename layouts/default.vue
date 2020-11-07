<template>
  <div>
    <CHeader />

    <CNavbar />

    <Nuxt />

    <CVisible base-class="fade" active-class="fade--show" once>
      <CFooter />
    </CVisible>
  </div>
</template>
