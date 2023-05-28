<template>
  <div class="d-flex flex-wrap singleLineItem">
    <div class="lineItemImg">
      <img :src="image"
           alt="product-image">
    </div>
    <div class="d-flex flex-column lineItemDetail">
      <h4 class="font-semi-bold">{{ title }}</h4>
      <div class="d-flex justify-space-between priceWithRemove">
        <p>${{ price }}</p>
        <button class="removeBtn" @click="handleItemRemove()">Remove</button>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "CartItem",
  props: {
    itemId: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      title: '',
      image: '',
      price: ''
    }

  },
  mounted() {
    this.fetchProduct()
  },
  methods: {
    fetchProduct() {
      const self = this
      this.$axios.get(`https://fakestoreapi.com/products/${this.itemId}`)
        .then(({data}) => {
          this.title = data.title
          this.image = data.image
          this.price = data.price
          self.$parent.totalCartPrice += self.price
        })
        .catch(error => {
          console.log("error -> ", error)
        })

    },
    handleItemRemove() {
      this.$emit('remove-item', this.itemId)
      this.$parent.totalCartPrice -= this.price
    }
  }

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
  object-fit: contain;
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
