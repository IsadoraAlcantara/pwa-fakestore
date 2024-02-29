<script setup>
import HomeOutline from 'vue-material-design-icons/HomeOutline.vue'
import DiamondStone from 'vue-material-design-icons/DiamondStone.vue'
import FaceManOutline from 'vue-material-design-icons/FaceManOutline.vue'
import FaceWomanOutline from 'vue-material-design-icons/FaceWomanOutline.vue'
import MonitorCellphone from 'vue-material-design-icons/MonitorCellphone.vue'
</script>
<template>
  <div class="tool-bar">
    <div class="header--logo">
      <img src="@/assets/logoFakeStore.png" alt="Logo" />
      <p class="logo-text">Fake store</p>
    </div>

    <div class="links">
      <ul :class="menuAberto ? 'menu' : ''">
        <div class="line">
          <HomeOutline class="icon" size="20px" />
          <li>Home</li>
        </div>
        <div class="line">
          <MonitorCellphone class="icon" size="20px" />
          <li>Eletrônicos</li>
        </div>
        <div class="line">
          <DiamondStone class="icon" size="20px" />
          <li>Joias</li>
        </div>
        <div class="line">
          <FaceManOutline class="icon" size="20px" />
          <li>Masculino</li>
        </div>
        <div class="line">
          <FaceWomanOutline class="icon" size="20px" />
          <li>Feminino</li>
        </div>
      </ul>
    </div>
  </div>
</template>
<style scoped>
.line {
  font-weight: 800;
  color: #797E8C;
  display: flex;
  margin: 1vw;
  gap: 15px;
  padding: 7px 10px;
  list-style: none;
}
.line:hover {
  background-color: #5D5ABF;
  border-radius: 5px;
}

.line:hover > .icon, .line:hover > li {
  color: white;
}
.tool-bar {
  box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
}
.header--logo {
  display: flex;
}

.header--logo p {
  margin-top: 2vw;
}
.header--logo img {
  width: 3rem;
  height: 3rem;
  margin: 1rem 1.5em 3em 1.5em;
}

.logo-text {
  color: #797E8C;
  font-size: 20px;
  font-weight: bold;
}

@media (max-width: 768px) {
  .tool-bar {
    display: none;
  }
}
</style>
