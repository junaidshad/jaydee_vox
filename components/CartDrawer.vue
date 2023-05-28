<template>
  <div class="cartDrawer" :class="{open: openCart}">
    <div class="d-flex drawerHeader justify-space-between">
      <h3 class="font-semi-bold">Your Cart(<span>{{cartItems.length}}</span>)</h3>
      <img class="close-cart" src="~assets/VoxelStoreAssets/close.svg" alt="close-cart" @click="handleCloseCart()">
    </div>
    <div class="drawerContent">
      <div class="listedLineItems">
        <template v-for="(itemId) in cartItems">
          <CartItem ref="cart-item" :key="itemId" :item-id="itemId.toString()" @remove-item="(id) => removeItem(id)"/>
        </template>
        <template v-if="!cartItems.length">
          <div class="d-flex justify-center"><h2>Cart is Empty</h2></div>
        </template>
      </div>
      <div class="drawerFooter">
        <div class="cartTotal d-flex font-semi-bold justify-space-between">
          <h2>Total</h2>
          <h2>${{totalCartPrice.toFixed(2) < 0 ? 0.00 : totalCartPrice.toFixed(2)}}</h2>
        </div>
        <div class="drawerCheckout">
          <button class="appCheckoutBtn">Continue to Checkout</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "CartDrawer",
  props: {
    openCart: {
      type: Boolean,
      default: false,
    }
  },
  data() {
    return {
      cartItems: [],
      totalCartPrice: 0
    }
  },
  watch: {
    openCart(val) {
      if(val) {
        this.cartItems = JSON.parse(localStorage.getItem('cartItems'))
      }
    }
  },
  methods: {
    handleCloseCart() {
      this.$emit('close-cart')
    },
    removeItem(id) {
      this.cartItems = this.cartItems.filter((item) => String(item) !== id)
      localStorage.setItem('cartItems', JSON.stringify(this.cartItems))
    }
  }
}
</script>

<style scoped>
.cartDrawer {
  max-width: 460px;
  width: 460px;
  position: fixed;
  right: 0;
  top: 0;
  z-index: 9;
  background-color: #fff;
  box-shadow: 0 0px 16px 0px rgb(197 197 197);
  height: 100vh;
  padding: 34px 32px;
  transition: all 0.3s ease-in-out;
  transform: translateX(100%);
}

.cartDrawer.open {
  transform: none
}

.drawerHeader {
  margin-bottom: 15px;
}

.drawerHeader h3 {
  font-size: 20px;
}

.drawerHeader img {
  max-width: 15px;
}

.listedLineItems {
  border: 1px solid rgba(26, 26, 26, 0.1);
  border-width: 1px 0 1px 0;
  padding: 24px 0;
  max-height: 700px;
  overflow-y: auto;
}

.cartTotal {
  padding: 20px 0;
  font-size: 20px;
}

.appCheckoutBtn {
  width: 100%;
  display: block;
  text-align: center;
  background-color: rgba(70, 45, 223, 1);
  color: #fff;
  border-radius: 8px;
  padding: 15px 0;
  transition: all 0.2s ease-in-out;
}

.appCheckoutBtn:hover {
  background-color: rgb(50, 33, 160);
}
.close-cart {
  cursor: pointer;
}

@media (max-width: 767px) {
  .cartDrawer {
    max-width: 100vw;
    padding: 30px 20px;
  }
}
</style>
