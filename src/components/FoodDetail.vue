<template>
  <div class="food-detail">
    <h2>Detail Makanan</h2>
    <FoodItem :food="food" />
    <slot></slot>
  </div>
</template>

<script>
import FoodItem from './FoodItem.vue';

export default {
  name: 'FoodDetail',
  components: {
    FoodItem
  },
  props: {
    food: Object
  }
}
</script>

<style scoped>
.food-detail {
  background-color: #f1f1f1;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
</style>
