<script setup>
import { ref } from 'vue'

import CartPlus from 'vue-material-design-icons/CartPlus.vue'
import Account from 'vue-material-design-icons/Account.vue'
import Menu from 'vue-material-design-icons/Menu.vue'
import Home from 'vue-material-design-icons/Home.vue'
import DiamondStone from 'vue-material-design-icons/DiamondStone.vue'
import FaceManOutline from 'vue-material-design-icons/FaceManOutline.vue'
import FaceWomanOutline from 'vue-material-design-icons/FaceWomanOutline.vue'
import MonitorCellphone from 'vue-material-design-icons/MonitorCellphone.vue'
import { useScreen } from '@/composables/screen'

const { browserWidth, deviceWidth, isMobile } = useScreen()

const menuAberto = ref(false)
</script>
<template>
  <header>

    <div class="header--logo">
      <img src="@/assets/logoFakeStore.png" alt="Logo" />
    </div>
    <div class="title">
      <h1>
        Produtos - {{ browserWidth }} - {{ deviceWidth }} - {{ isMobile }}
        <span v-if="isMobile">É móvel</span>
      </h1>
      <span id='topo'></span>
    </div>
    <nav>
      <ul :class="menuAberto ? 'menu' : ''">
        <div class="line">
          <Home class="icon" size="20px" />
          <li>Home</li>
        </div>
        <div class="line">
          <MonitorCellphone class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Eletrônicos</li>
        </div>
        <div class="line">
          <DiamondStone class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Joias</li>
        </div>
        <div class="line">
          <FaceManOutline class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Masculino</li>
        </div>
        <div class="line">
          <FaceWomanOutline class="icon" size="20px" @click="menuAberto = !menuAberto" />
          <li>Feminino</li>
        </div>
      </ul>
    </nav>
    <div class="header--icons">
      <Account class="icon-nav" />
      <CartPlus class="icon-nav" />
      <Menu class="menu-hamburger icon-nav" @click="menuAberto = !menuAberto" />
    </div>
  </header>
</template>
<style scoped>
header {
  padding: 0.2rem 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav ul {
  display: none;
  gap: 1rem;
}

nav li {
  list-style: none;
  font-weight: 500;
  color: #5155a6;
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

.icon-nav {
  color: #5155a6;
}

.header--logo {
  display: none;
}

.title {
  margin: 2vw;
  display: flex;
}
.title h1 {
  color: #5155a6;
}

@media (max-width: 768px) {
  header {
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    height: 10vw !important;
  }

  nav ul {
    display: none;
  }

  .title {
    display: none;
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

  .line .icon,
  .line li {
    color: #797e8c;
  }

  .line:hover > .icon,
  .line:hover > li {
    color: white;
  }
  .line {
    display: flex;
    gap: 1vw;
    padding: 5px 7px;
  }

  .line:hover {
    background-color: #7e81bf;
    border-radius: 5px;
  }
}
</style>
