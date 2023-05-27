<template>
  <div>
    <div class="hero">
      <div>Welcome to Voxel</div>
      <span>Discover our wide range of products</span>
    </div>

    <div class="container main-page">
      <CategoryFilter />
      <div class="grid-view">
        <Product />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',

}
</script>
