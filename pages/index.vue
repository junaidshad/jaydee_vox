<template>
  <div>
    <div class="hero d-flex flex-column align-center justify-center">
      <h1>Welcome to Voxel</h1>
      <p>Discover our wide range of products</p>
    </div>

    <div class="main-page">
      <CategoryFilter :active-category="activeCategory" :categories="categories"/>
      <div class="appContainer d-flex flex-wrap grid-view">
        <template v-for="(product) in filteredProducts" >
          <Product :key="product.id" :product="product" @open-cart="openCartDrawer()" />
        </template>
      </div>
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
      categories: [{name: 'all', isActive: true}],
      products: [],
    }
  },
  computed: {
    activeCategory() {
      return this.categories.find((category) => category.isActive).name
    },
    filteredProducts() {
      return this.products.filter((product) => {
        if(this.activeCategory === 'all') return true
        return product.category === this.activeCategory
      })
    }
  },
  beforeMount() {
    this.fetchCategories()
    this.fetchProducts()
  },
  methods: {
    closeCart() {
      this.$parent.openCart = false
    },
    openCartDrawer() {
      this.$parent.openCart = true
    },
    fetchCategories() {
      this.$axios.get('https://fakestoreapi.com/products/categories')
        .then(({data}) => {
          this.categories = [...this.categories, ...data.map(item => {
            return {name: item, isActive: false}
          })]
        })
        .catch((error) => {
          console.log("error -> ", error)
        })
    },
    fetchProducts() {
      this.$axios.get('https://fakestoreapi.com/products')
        .then(({data}) => {
          this.products = data
        })
        .catch((error) => {
          console.log("error -> ", error)
        })
    }
  }
}
</script>

<style scoped>
.grid-view{
  margin-top: 24px;
  gap: 12px;
}

.hero {
  height: 380px;
  background-color: gainsboro;
}

.hero h1 {
  font-size: 34px;
  line-height: 42px;
  margin-bottom: 10px;
  font-family: 'InstrumentSemiBold',sans-serif;
}

.hero p {
  font-weight: 500;
  line-height: 20px;
  font-size: 16px;
  color: rgba(26, 26, 26, 0.5);
}

@media(min-width: 768px) and (max-width: 991px){
  .grid-view{
    margin-top: 24px;
    gap: 12px;
  }
}

</style>
