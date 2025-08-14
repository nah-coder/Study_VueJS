<script setup>
import { computed, ref } from 'vue';
import TheWelcome from '../components/TheWelcome.vue'

const count = ref(10);

const handleIncrease = () => {
  count.value++;
  console.log('imit data');
};


const categoryProduct = ref('food');


const products = ref([
  { id: 1, name: 'Pizza',category:'food', price: 5000 },
  { id: 2, name: 'Tra sua',category:'drink', price: 5000 },
  { id: 3, name: 'Nước ngọt',category:'drink', price: 5000 }
]);


const handleChangeCategoryProduct = (value) => {
  categoryProduct.value = value;
};


const productFilter = computed(() => {
  return products.value.filter(product => product.category === categoryProduct.value);
})
</script>

<template>
  <main>
    <TheWelcome :countView="count" @handle-increase="handleIncrease"/>

    <button @click="handleChangeCategoryProduct('food')">Hiển thị food</button>
    <button @click="handleChangeCategoryProduct('drink')">Hiển thị drink</button>


    <div v-if="categoryProduct==='food'">
      Danh sách sản phẩm food
    </div>
    <div v-else-if="categoryProduct==='drink'">
      Danh sách sản phẩm drink
    </div>
    <div v-for="product in productFilter">
      <div class="group-product-item">
        <h2>{{ product.name }}</h2>
        <p>Price: {{ product.price }} VND</p>
        <p>category: {{ product.category }} VND</p>
      </div>
    </div>
  </main>
</template>
