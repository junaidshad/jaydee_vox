<template>
  <div class="footer">
    <div class="appContainer align-center container d-flex footer justify-center">
      <div class="logo">Voxel <span>Store</span></div>
    </div>
  </div>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Foot"
})
</script>

<style scoped>
.footer {
  //position: sticky;
  bottom: 0;
  background-color: #fff;
  height: 64px;
  border-top: 1px solid rgba(26, 26, 26, 0.1);
  margin-top: 30px;
}

.footer .appContainer {
  height: 100%;
}

</style>
