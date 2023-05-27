<template>
  <div class="cartDrawer" :class="{open: openCart}">
    <div class="d-flex drawerHeader justify-space-between">
      <h3 class="font-semi-bold">Your Cart(<span>2</span>)</h3>
      <img @click="handleCloseCart()" class="close-cart" src="~assets/VoxelStoreAssets/close.svg" alt="close-cart">
    </div>
    <div class="drawerContent">
      <div class="listedLineItems">
        <CartItem />
        <CartItem />
        <CartItem />
<!--        <div class="d-flex flex-wrap singleLineItem">
          <div class="lineItemImg">
            <img src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI"
                 alt="product-image">
          </div>
          <div class="d-flex flex-column justify-space-between lineItemDetail">
            <h4 class="font-semi-bold">Fjallraven - Foldsack No. 1 Backpack, Fits 15 Laptops</h4>
            <div class="d-flex justify-space-between priceWithRemove">
              <p>$219.90</p>
              <button class="removeBtn">Remove</button>
            </div>
          </div>
        </div>
        <div class="d-flex flex-wrap singleLineItem">
          <div class="lineItemImg">
            <img src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI"
                 alt="product-image">
          </div>
          <div class="d-flex flex-column justify-space-between lineItemDetail">
            <h4 class="font-semi-bold">Fjallraven - Foldsack No. 1 Backpack, Fits 15 Laptops</h4>
            <div class="d-flex justify-space-between priceWithRemove">
              <p>$219.90</p>
              <button class="removeBtn">Remove</button>
            </div>
          </div>
        </div>-->
      </div>
      <div class="drawerFooter">
        <div class="cartTotal d-flex font-semi-bold justify-space-between">
          <h2>Total</h2>
          <h2>$242.20</h2>
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
      default: false
    }
  },
  methods: {
    handleCloseCart() {
      this.$emit('close-cart')
    }
  }
}
</script>

<style scoped>
.cartDrawer {
  max-width: 460px;
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

@media (max-width: 767px) {
  .cartDrawer {
    max-width: 430px;
    padding: 30px 20px;
  }
}
</style>
