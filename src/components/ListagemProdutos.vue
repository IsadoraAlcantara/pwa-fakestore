<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";
import BarButton from "./BarButton.vue";
import { useScreen } from '@/composables/screen';

const { isMobile } = useScreen();
const produtos = ref([]);

onMounted(async () => {
  const response = await axios.get("https://fakestoreapi.com/products");
  produtos.value = response.data;
});

const formatPrice = (price) => `R$ ${price.toFixed(2).replace(".", ",")}`;
</script>
<template>
  <div>
    <div class="container">
      <div class="card" v-for="produto in produtos" :key="produto.id">
        <div>
          <img class="card--avatar" :src="produto.image" :alt="produto.title" />
        </div>
        <div class="text">
          <h2 class="card--title">{{ produto.title }}</h2>
          <p class="description">{{ produto.description.slice(0, 70) + "..." }}</p>
          <div class="card-details">
            <button>Saiba mais</button>
            <p class="price">{{ formatPrice(produto.price) }}</p>
          </div>
        </div>
      </div>
    </div>
    <BarButton v-if="isMobile" />
  </div>
</template>
<style scoped>
@media (max-width: 768px) {
  .card {
    width: 90% !important;
    height: 25vh !important;
  }

  .card--avatar {
    width: 12rem !important;
  }

  button {
    height: 10vw;
    text-wrap: nowrap;
  }

  .card--title {
    font-size: 1rem !important;
  }

  .description {
    font-size: 0.9rem !important;
    margin-top: 0 !important; 
  }

  .price {
    font-size: 0.8rem !important;
  }

  .container {
    margin: 7vw 0 20vw 0 !important;
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  .card {
    width: 22rem;
  }
  
  .card--avatar {
    width: 34rem;
  }

  .title {
    display: flex;
  }
}

@media (min-width: 768px) and (max-width: 970px) {
  .card {
      width: 35vw !important;
      height: 23vw !important;
  }

  .card--title {
    font-size: 1rem !important;
  }

  .description {
    font-size: 0.8rem;
  }

  button {
    height: 4vw;
    font-size: 0.7rem;
  }
}

.text {
  width: 50%;
}

.description {
  color: #565d73;
  margin-bottom: 1vw;
}

.price {
  margin-top: 1vw;
}
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;  align-items: center;
  margin: auto;
}
.card {
  padding: 2vw;
  display: flex;
  justify-content: space-between;
  width: 35vw;
  height: 17rem;
  background: #f4f4fe;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  border-radius: 10px;
  margin: 0 0 2vw 3vw;
  overflow: hidden;
}

.card--avatar {
  width: 13vw;
  height: 13rem;
  object-fit: contain;
  margin-bottom: 0.5rem;
  border-radius: 2vw;
}
.card--title {
  color: #222;
  font-weight: 700;
  text-transform: capitalize;
  font-size: 1.1rem;
  margin-top: 0.5rem;
}

.card-details {
  display: flex;
  gap: 10%;
}

button {
  background-color: #7e81bf;
  color: white;
  padding: 10px 20px;
  border: 0;
  border-radius: 8px;
  margin-top: 0.5vw;
}

button:hover {
  background-color: #5155a6;
}
</style>
