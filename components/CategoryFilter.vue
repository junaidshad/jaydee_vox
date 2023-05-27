<template>
  <div class="category-filters">
    <div class="appContainer">
      <div class="d-flex align-center smallHide">
        <div v-for="(category, index) in categories" :key="index">
          <button class="category-btn d-block font-semi-bold" :class="{ active : category.isActive}" @click="handleCategoryClick(category.name)">{{category.name}}</button>
        </div>
      </div>
      <div class="medium-up-hide categorySelect">
        <select class="d-block font-semi-bold">
          <option v-for="(category, index) in categories" :key="index">
            {{category.name}}
          </option>
        </select>
        <img class="expandIcon" alt="expand-more" src="~assets/VoxelStoreAssets/expand_more.svg">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CategoryFilter",
  props: {
    categories: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    handleCategoryClick(categoryName) {
      this.categories.forEach((category) => {
        category.isActive = category.name === categoryName
      })
    }
  }
}
</script>

<style scoped>

.category-filters{
  border-bottom: 1px solid rgba(26, 26, 26, 0.1);
  position: sticky;
  top: 64px;
  background-color: #fff;
}
.category-btn {
  padding: 27px 0;
  color: rgba(26, 26, 26, 0.5);
  font-size: 14px;
  margin-right: 18px;
  text-transform: capitalize;
}
.category-btn.active{
  color: #1A1A1A;
  position: relative;
}
button.category-btn.d-block.font-semi-bold.active:after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 3px;
  background-color: #1A1A1A;
  border-radius: 4px 4px 0px 0px;
}
.categorySelect{position: relative;}
.categorySelect select{
  width: 100%;
  border: 1px solid rgba(26, 26, 26, 0.1);
  height: 60px;
  padding: 0 15px;
  border-radius: 8px;
  margin: 20px 0;
  -webkit-appearance: none;
  position: relative;
}
.categorySelect img{
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);
}

@media(min-width: 768px) and (max-width: 991px){
  .category-btn {
    padding: 20px 0;
    margin-right: 16px;
  }
}

</style>
