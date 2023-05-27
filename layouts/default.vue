<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "default",
  data() {
    return {
      openCart: false
    }
  }
})
</script>

<template>
  <div>
    <HeadNavigation />
    <NuxtChild :open-cart="openCart" />
    <Foot />
  </div>
</template>

<style scoped>

</style>
