<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'
const produtos = ref([])

onMounted(async () => {
  const response = await axios.get('https://fakestoreapi.com/products')
  produtos.value = response.data
})

const formatPrice = (price) => `R$ ${price.toFixed(2).replace('.', ',')}`
</script>
<template>
  <div>
    <h1 class="title">Produtos</h1>
    <div class="container">
      <div class="card" v-for="produto in produtos" :key="produto.id">
        <div>
          <img class="card--avatar" :src="produto.image" :alt="produto.title" />
        </div>
        <div class="text">
          <h1 class="card--title">{{ produto.title }}</h1>
          <p class="description">{{ produto.description }}</p>
          <p class="price">{{ formatPrice(produto.price) }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
@media (max-width: 768px) {
  .container {
    gap: 0.5rem;
  }
  .card {
    width: 90%;
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  .card {
    width: 22rem;
  }
}

.text {
  width: 50%;
}

.title {
  margin: 2vw 0 0 4vw;
}

.description {
  color: #565D73;
}

.price {
  margin-top: 1vw;
}
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
  align-items: center;
  margin: auto;
  padding: 1rem 0;
}
.card {
  padding: 2vw;
  display: flex;
  justify-content: space-between;
  width: 40rem;
  height: 25rem;
  background: #fff;
  box-shadow:
    0 10px 20px rgba(0, 0, 0, 0.19),
    0 6px 6px rgba(0, 0, 0, 0.23);
  border-radius: 10px;
  margin: auto;
  overflow: hidden;
}
.card--avatar {
  width: 17vw;
  height: 17rem;
  object-fit: cover;
  margin-bottom: 0.5rem;
  border-radius: 1vw;
}
.card--title {
  color: #222;
  font-weight: 700;
  text-transform: capitalize;
  font-size: 1.1rem;
  margin-top: 0.5rem;
}
</style>
