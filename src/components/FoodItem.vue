<template>
    <div class="food-item">
      <h3>Detail Makanan</h3>
      <p><strong>Nama:</strong> {{ food.name }}</p>
      <p><strong>Deskripsi:</strong> {{ food.description }}</p>
      <p><strong>Harga:</strong> {{ food.price }}</p>
    </div>
</template>
  
<script>
  export default {
    name: 'FoodItem',
    props: {
      food: Object
    }
  }
</script>
  
<style scoped>
  .food-item {
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 20px;
  }
</style>
  