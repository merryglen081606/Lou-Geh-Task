<template>
  <!-- <Tutorial/> --> 
  <div class="login__layout">
    <div class="login__loginform">
      <div class="login__image"></div>
      <div class="login__title"><h2>Lou Geh Tasks</h2></div>
      <input type="text" placeholder="Username" class="login__input">
      <input type="password" placeholder="Password" class="login__input">
      <input type="button" value="Login" class="login__button">
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style lang="scss">
.login{
  &__image{
    background-image: url("../static/bfi_gradient.png");
    height: 70px;
    width: 70px;
    margin-bottom: 30px;
    background-size: 90%;
    background-position: center;
    background-repeat: no-repeat;
    margin: auto;
    margin-bottom: 20px;
  }
}
</style>
