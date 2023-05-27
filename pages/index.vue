<template>
  <div>
    <div class="hero d-flex felx-column align-center justify-center flex-column">
      <h1>Welcome to Voxel</h1>
      <p>Discover our wide range of products</p>
    </div>

    <div class="main-page">
      <CategoryFilter/>
      <Product/>
      <CartDrawer :open-cart="openCart" @close-cart="closeCart()"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  props: {
    openCart: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {

    }
  },
  methods: {
    closeCart() {
      this.$parent.openCart = false
    }
  }
}
</script>

<style scoped>
.hero {
  height: 380px;
  background-color: gainsboro;
}

.hero h1 {
  font-size: 34px;
  line-height: 42px;
  margin-bottom: 10px;
  font-family: 'InstrumentSemiBold';
}

.hero p {
  font-weight: 500;
  line-height: 20px;
  font-size: 16px;
  color: rgba(26, 26, 26, 0.5);
}


</style>
