<script setup>
import ListagemProdutos from '@/components/ListagemProdutos.vue'
import MenuSuperior from '@/components/MenuSuperior.vue'
import ToolBar from '@/components/ToolBar.vue'
import FooterComponent from '@/components/Footer/FooterComponent.vue'

import { useScreen } from '@/composables/screen'

const { isMobile } = useScreen()
</script>

<template>
  <div class="main-container">
    <div>
      <ToolBar class="tool-bar" />
    </div>
    <div>
      <MenuSuperior />
      <component :is="menu" />
      <main>
        <router-view />
      </main>
    </div>
  </div>

  <FooterComponent v-if="!isMobile" class="footer" />
</template>
<style scoped>
.main-container {
  display: grid;
  grid-template-columns: 15% 85%;
}

@media (max-width: 768px) {
  .main-container {
    grid-template-columns: 100%;
  }
}

.tool-bar {
  height: 100%;
  position: fixed;
}

.menu {
  height: 4vw;
}
.produtos {
  widows: 80%;
}
</style>
