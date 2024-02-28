<script setup>
import { ref } from 'vue'

import CartPlus from 'vue-material-design-icons/CartPlus.vue'
import Account from 'vue-material-design-icons/Account.vue'
import Menu from 'vue-material-design-icons/Menu.vue'
import Home from 'vue-material-design-icons/Home.vue'
import DiamondStone from 'vue-material-design-icons/DiamondStone.vue'
import HumanMale from 'vue-material-design-icons/HumanMale.vue'
import HumanFemale from 'vue-material-design-icons/HumanFemale.vue'
import MonitorCellphone from 'vue-material-design-icons/MonitorCellphone.vue'

const menuAberto = ref(false)
</script>
<template>
  <header>
    <div class="header--logo">
      <img src="@/assets/logoFakeStore.png" alt="Logo" />
    </div>
    <nav>
      <ul :class="menuAberto ? 'menu' : ''">
        <div class="line">
          <Home class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Home</li>
        </div>
        <div class="line">
          <MonitorCellphone class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Eletrônicos</li>
        </div>
        <div class="line">
          <DiamondStone class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Jóias</li>
        </div>
        <div class="line">
          <HumanMale class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Masculino</li>
        </div>
        <div class="line">
          <HumanFemale class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Feminino</li>
        </div>  
      </ul>
    </nav>
    <div class="header--icons">
      <Account />
      <CartPlus />
      <Menu class="menu-hamburger" @click="menuAberto = !menuAberto" />
    </div>
  </header>
</template>
<style scoped>
header {
  background: #fff;
  box-shadow:
    0 10px 20px rgba(0, 0, 0, 0.19),
    0 6px 6px rgba(0, 0, 0, 0.23);
  padding: 0.2rem 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header--logo {
  display: flex;
  align-items: center;
}
.header--logo img {
  width: 3rem;
  height: 3rem;
  margin-right: 0.5rem;
}
nav ul {
  display: flex;
  gap: 1rem;
}
nav li {
  list-style: none;
}

.header--icons {
  display: flex;
  gap: 1rem;
}
.menu-hamburger {
  display: none;
}

.icon {
  display: none;
}

@media (max-width: 768px) {
  nav ul {
    display: none;
  }
  .menu-hamburger {
    display: block;
  }

  .icon {
    display: block;
  }

  nav .menu {
    height: 37%;
    display: flex;
    flex-direction: column;
    position: absolute;
    background-color: rgba(255, 255, 255, 0.9);
    box-shadow:
      0 10px 20px rgba(0, 0, 0, 0.19),
      0 6px 6px rgba(0, 0, 0, 0.23);
    border-radius: 10px;
    right: 0;
    text-align: left;
    padding: 15px 16px 0 10px;
  }
  nav .menu li {
    display: block;
    padding-left: 1vw;
  }

.line .icon, .line li {
  color: #4f4f50;
}


.line:hover > .icon, .line:hover > li {
    color: #222629;
  }
  .line {
    display: flex;
    gap: 1vw;
    padding: 5px 7px;
  }

  .line:hover {
    background-color: #EFEFEF;
    border-radius: 5px;
  }
}
</style>
