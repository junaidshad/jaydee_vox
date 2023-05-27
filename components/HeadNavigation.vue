<template>
  <div class="header-navigation">
    <div class="appContainer d-flex justify-space-between align-center">
      <div class="logo">Voxel <span>Store</span></div>
      <img @click="handleClickCart()" src="~assets/VoxelStoreAssets/bag.svg" alt="cart-bag" width="18" height="21"/>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "HeadNavigation",
  mounted() {
    console.log("THIS -> ", this.$parent)
  },
  methods: {
    handleClickCart() {
      this.$parent.openCart = true
    }
  }
}
</script>

<style scoped>
.header-navigation {
  height: 64px;
  position: sticky;
  top: 0;
  background-color: #fff;
  box-shadow: 0 0 2px 1px #ccc;
  z-index: 9;
}

.header-navigation .appContainer {
  height: 100%;
}

</style>
