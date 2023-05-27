<template>
  <div class="appContainer d-flex flex-wrap grid-view">
    <div class="product-card">
      <img class="productImg" src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI" alt="product-image">
      <div class="product-content">
        <div class="font-semi-bold product-title">Raven - Foldsack No. 1 Backpack, Fits 15 Laptops</div>
        <div class="font-semi-bold product-price">$109.95</div>
        <button class="align-center btn-add-cart d-flex font-semi-bold justify-center"><img src="~assets/VoxelStoreAssets/add.svg" alt="button-add">Add to Cart</button>
      </div>
    </div>
    <div class="product-card">
      <img class="productImg" src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI" alt="product-image">
      <div class="product-content">
        <div class="font-semi-bold product-title">Raven - Foldsack No. 1 Backpack, Fits 15 Laptops</div>
        <div class="font-semi-bold product-price">$109.95</div>
        <button class="align-center btn-add-cart d-flex font-semi-bold justify-center"><img src="~assets/VoxelStoreAssets/add.svg" alt="button-add">Add to Cart</button>
      </div>
    </div>
    <div class="product-card">
      <img class="productImg" src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI" alt="product-image">
      <div class="product-content">
        <div class="font-semi-bold product-title">Raven - Foldsack No. 1 Backpack, Fits 15 Laptops</div>
        <div class="font-semi-bold product-price">$109.95</div>
        <button class="align-center btn-add-cart d-flex font-semi-bold justify-center"><img src="~assets/VoxelStoreAssets/add.svg" alt="button-add">Add to Cart</button>
      </div>
    </div>
    <div class="product-card">
      <img class="productImg" src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI" alt="product-image">
      <div class="product-content">
        <div class="font-semi-bold product-title">Raven - Foldsack No. 1 Backpack, Fits 15 Laptops</div>
        <div class="font-semi-bold product-price">$109.95</div>
        <button class="align-center btn-add-cart d-flex font-semi-bold justify-center"><img src="~assets/VoxelStoreAssets/add.svg" alt="button-add">Add to Cart</button>
      </div>
    </div>
    <div class="product-card">
      <img class="productImg" src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI" alt="product-image">
      <div class="product-content">
        <div class="font-semi-bold product-title">Raven - Foldsack No. 1 Backpack, Fits 15 Laptops</div>
        <div class="font-semi-bold product-price">$109.95</div>
        <button class="align-center btn-add-cart d-flex font-semi-bold justify-center"><img src="~assets/VoxelStoreAssets/add.svg" alt="button-add">Add to Cart</button>
      </div>
    </div>
    <div class="product-card">
      <img class="productImg" src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI" alt="product-image">
      <div class="product-content">
        <div class="font-semi-bold product-title">Raven - Foldsack No. 1 Backpack, Fits 15 Laptops</div>
        <div class="font-semi-bold product-price">$109.95</div>
        <button class="align-center btn-add-cart d-flex font-semi-bold justify-center"><img src="~assets/VoxelStoreAssets/add.svg" alt="button-add">Add to Cart</button>
      </div>
    </div>
    <div class="product-card">
      <img class="productImg" src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI" alt="product-image">
      <div class="product-content">
        <div class="font-semi-bold product-title">Raven - Foldsack No. 1 Backpack, Fits 15 Laptops</div>
        <div class="font-semi-bold product-price">$109.95</div>
        <button class="align-center btn-add-cart d-flex font-semi-bold justify-center"><img src="~assets/VoxelStoreAssets/add.svg" alt="button-add">Add to Cart</button>
      </div>
    </div>
  </div>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Product"
})
</script>

<style scoped>
.grid-view{
  margin-top: 24px;
  gap: 12px;
}
.product-card{
  padding: 24px;
  border: 1px solid rgba(26, 26, 26, 0.1);
  border-radius: 12px;
  width: 24%;
}
.product-card .productImg{
  max-width: 290px;
  margin: 0 auto;
  display: block;
  width: 100%;
}
.product-content{margin-top: 28px;}
.product-title {line-height: 20px;}
.product-price{
  color: rgba(26, 26, 26, 0.5);
  padding-top: 4px;
}
.btn-add-cart {
  gap: 6px;
  border-radius: 12px;
  background: #F4F4F4;
  width: 100%;
  padding: 13px 16px;
  margin-top: 18px;
  transition: all 0.2s ease-in-out;
}
.btn-add-cart:hover{background: #d7d7d7;}
.btn-add-cart img {
  width: 24px;
  height: 24px;
}

@media(min-width: 992px) and (max-width: 1199px){
  .product-card{padding: 15px;}
  .product-content {
    margin-top: 15px;
    font-size: 14px;
  }
  .btn-add-cart{margin-top: 15px;}
}

@media(min-width: 768px) and (max-width: 991px){
  .grid-view{
    margin-top: 24px;
    gap: 12px;
  }
  .product-card{
    padding: 14px;
    width: 32%;
  }
  .product-content {
    margin-top: 12px;
    font-size: 12px;
  }
  .product-title{line-height: 18px;}
  .btn-add-cart{margin-top: 12px;}
}
@media(max-width: 767px){
  .product-card{width: 100%;}
}

</style>
