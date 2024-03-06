<script setup>
import ButtonBack from './ButtonBack.vue'

const scrollTop = function() {
    window.scrollTo(0, 0);
};
</script>
<template>
  <ButtonBack />
  <div class="footer">
    <div>
      <h2>Conheça-nos</h2>
      <p>Sobre nós</p>
      <p>Acessibilidade</p>
      <p>Carreiras</p>
      <p>Comunidade</p>
    </div>
    <div>
      <h2>Contatos</h2>
      <p>Sobre</p>
      <p>Instagram</p>
      <p>Whatsapp</p>
    </div>
    <div>
      <h2>Pagamento</h2>
      <p>Meios de pagamento</p>
      <p>Compre com pontos</p>
      <p>Cartão de crédito</p>
    </div>
    <div>
      <h2>Ajuda</h2>
      <p>Sua conta</p>
      <p>Frete e prazo de entrega</p>
      <p>Devoluções e reembolso</p>
      <p>Ajuda</p>
    </div>
  </div>
</template>
<style scoped>
.footer {
  background-color: #210b40;
  color: #c8c1d9;
  display: flex;
  gap: 10vw;
  justify-content: center;
  padding-bottom: 2vw;
}

.logo {
  font-size: 20px;
  display: flex;
  align-self: center;
}

p {
  margin: 1vh 0;
  font-size: 14px;
  color: white;
}

h2 {
  color: white;
  font-size: 16px;
  margin-top: 3vh;
}

</style>
