<template>
  <nav-bar class="cart-nav-background">
      <slot slot="center">购物车</slot>
  </nav-bar>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
export default {
  components: {
    NavBar
  }
}
</script>

<style>
  .cart-nav-background {
    background-color: var(--color-tint);
    color: var(--color-background);
  }
</style>
