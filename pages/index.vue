<template>
  <main>
    <CVisible base-class="move move--from-left" active-class="move--show" once>
      <CStory />
    </CVisible>

    <CVisible base-class="move move--from-right" active-class="move--show" once>
      <CCapabilities />
    </CVisible>

    <CVisible base-class="fade" active-class="fade--show" once>
      <CAmazing />
      <CSignupForm />
    </CVisible>
  </main>
</template>
<script>
export default {
  name: 'IndexPage',
  layout: 'home',
}
</script>

<style lang="scss">
.fade {
  opacity: 0;
  transition: opacity 0.3s ease-in;

  &--show {
    opacity: 1;
  }
}

.move {
  transition: opacity 0.3s ease-in, transform 0.6s ease-out;

  &--from-left {
    opacity: 0;
    transform: translateX(-10rem);
  }

  &--from-right {
    opacity: 0;
    transform: translateX(10rem);
  }

  &--show {
    opacity: 1;
    transform: translateX(0);
  }
}
</style>
