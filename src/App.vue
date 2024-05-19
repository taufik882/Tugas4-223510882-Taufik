<template>
  <div class="app">
    <header>
      <h1>Food App</h1>
    </header>
    <main>
      <div class="content">
        <FoodList :foods="foods" @food-selected="handleFoodSelected" />
        <FoodDetail v-if="selectedFood" :food="selectedFood">
          <template v-slot>
            <p><strong>Informasi Tambahan:</strong> Ini adalah beberapa informasi tambahan tentang makanan ini.</p>
          </template>
        </FoodDetail>
      </div>
    </main>
  </div>
</template>

<script>
import FoodList from './components/FoodList.vue';
import FoodDetail from './components/FoodDetail.vue';

export default {
  name: 'App',
  components: {
    FoodList,
    FoodDetail
  },
  data() {
    return {
      foods: [
        { id: 1, name: 'Nasi Goreng', description: 'Nasi yang digoreng dengan bumbu dan sayuran', price: 'Rp 20.000' },
        { id: 2, name: 'Sate Ayam', description: 'Daging ayam yang ditusuk dan dibakar', price: 'Rp 25.000' },
        { id: 3, name: 'Gado-Gado', description: 'Salad sayuran dengan saus kacang', price: 'Rp 15.000' },
        { id: 4, name: 'Rendang', description: 'Daging sapi dimasak dengan bumbu rempah khas Padang', price: 'Rp 35.000' },
        { id: 5, name: 'Bakso', description: 'Bola daging yang disajikan dengan kuah kaldu', price: 'Rp 18.000' },
        { id: 6, name: 'Soto Ayam', description: 'Sup ayam dengan kuah kuning dan bumbu rempah', price: 'Rp 22.000' },
        { id: 7, name: 'Mie Goreng', description: 'Mie yang digoreng dengan bumbu dan sayuran', price: 'Rp 17.000' },
        { id: 8, name: 'Ayam Goreng', description: 'Daging ayam yang digoreng dengan tepung', price: 'Rp 20.000' },
        { id: 9, name: 'Nasi Uduk', description: 'Nasi yang dimasak dengan santan dan rempah-rempah', price: 'Rp 18.000' },
        { id: 10, name: 'Pempek', description: 'Makanan khas Palembang dari ikan dan tepung sagu', price: 'Rp 25.000' }
      ],
      selectedFood: null
    }
  },
  methods: {
    handleFoodSelected(food) {
      this.selectedFood = food;
    }
  }
}
</script>

<style scoped>
.app {
  font-family: 'Arial', sans-serif;
  color: #333;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header {
  background-color: #4caf50;
  color: white;
  padding: 20px;
  text-align: center;
}

main {
  padding: 20px;
}

.content {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  justify-content: center;
}

@media (max-width: 768px) {
  .content {
    flex-direction: column;
    align-items: center;
  }
}
</style>
