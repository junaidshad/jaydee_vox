<script>
export default {
  name: "CategoryFilter",
  data() {
    return {
      categories: [
        {name: 'All', value: 'all' },
        {name: 'Jewelery', value: 'jewelery' },
        {name: 'Electronics', value: 'electronics' },
        {name: 'Men\'s Clothing', value: 'mens_clothing' },
        {name: 'Women\'s Clothing', value: 'womens_clothing' },
      ]
    }
  }
}
</script>

<template>
  <div class="category-filters">
    <div v-for="(category, index) in categories" :key="index">
      <button class="category-btn">{{category.name}}</button>
    </div>
  </div>
</template>

<style scoped>

</style>
