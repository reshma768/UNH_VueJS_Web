<!-- FoodBox.vue -->
<template>
  <div>
    <div v-for="item of foods" :key="item.id">
      <SingleFood :food="item" />
    </div>
  </div>
</template>

<script>
import SingleFood from './SingleFood.vue';

export default {
  name: 'FoodBox',
  props: {
    foods: Array,
  },
  components: {
    SingleFood,
  },
};
</script>

<style scoped>
/* ... */
</style>
