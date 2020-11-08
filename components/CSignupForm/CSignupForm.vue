<template>
  <form class="c-signup-form">
    <label for="c-signup-form__input" class="c-signup-form__label"
      >Newsletter Signup</label
    >
    <input
      id="c-signup-form__input"
      type="email"
      class="c-signup-form__input"
      placeholder="text@youremail.com"
    />
    <CButton class="c-signup-form__button" variant="primary">Signup</CButton>
  </form>
</template>
<style lang="scss" src="./CSignupForm.scss" scoped />
