<script>
import {defineComponent} from 'vue'

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Product"
})
</script>

<template>
  <div class="product-card">
    <img src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI" alt="product-image">
    <div class="product-content">
      <div class="product-title">Raven - Foldsack No. 1 Backpack, Fits 15 Laptops</div>
      <div class="product-price">$109.95</div>
      <button class="btn-add-cart"><img src="~assets/VoxelStoreAssets/add.svg" alt="button-add">Add to Cart</button>
    </div>
  </div>
</template>

<style scoped>

</style>
