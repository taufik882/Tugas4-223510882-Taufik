<template>
    <div class="food-list">
      <h2>Daftar Makanan</h2>
      <ul>
        <li v-for="food in foods" :key="food.id" @click="selectFood(food)">
          {{ food.name }}
        </li>
      </ul>
    </div>
</template>
  
<script>
  export default {
    name: 'FoodList',
    props: {
      foods: Array
    },
    methods: {
      selectFood(food) {
        this.$emit('food-selected', food);
      }
    }
  }
</script>
  
<style scoped>
  .food-list {
    background-color: #f9f9f9;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  .food-list h2 {
    margin-bottom: 15px;
  }
  .food-list ul {
    list-style-type: none;
    padding: 0;
  }
  .food-list li {
    padding: 10px;
    border-bottom: 1px solid #ddd;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  .food-list li:hover {
    background-color: #e0f7fa;
  }
</style>
  