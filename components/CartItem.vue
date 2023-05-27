<template>
  <div class="d-flex flex-wrap singleLineItem">
    <div class="lineItemImg">
      <img src="https://fastly.picsum.photos/id/41/1280/805.jpg?hmac=W9CWeYdlZisqEfhjuODl83T3lCXAqjUZrOe9iMFPYmI"
           alt="product-image">
    </div>
    <div class="d-flex flex-column lineItemDetail">
      <h4 class="font-semi-bold">Fjallraven - Foldsack No. 1 Backpack, Fits 15 Laptops</h4>
      <div class="d-flex justify-space-between priceWithRemove">
        <p>$219.90</p>
        <button class="removeBtn">Remove</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CartItem",

}
</script>

<style scoped>
.singleLineItem {
  margin-bottom: 15px;
}

.listedLineItems .singleLineItem:nth-last-child(1) {
  margin-bottom: 0;
}

.lineItemImg {
  max-width: 102px;
  padding: 14px;
  border: 1px solid rgba(26, 26, 26, 0.1);
  width: 30%;
  border-radius: 8px;
}

.lineItemImg img {
  width: 70px;
  height: 70px;
  object-fit: cover;
}

.lineItemDetail {
  padding-left: 20px;
  width: 70%;
  justify-content: center;
}

.lineItemDetail h4 {
  line-height: 19px;
  margin-bottom: 13px;
  font-size: 15px;
}

.priceWithRemove {
  color: rgba(26, 26, 26, 0.5);
  font-size: 16px;
}

@media (max-width: 767px) {

  .lineItemImg {
    max-width: 80px;
    padding: 14px;
  }

  .lineItemImg img {
    width: 50px;
    height: 50px;
  }
}
</style>
