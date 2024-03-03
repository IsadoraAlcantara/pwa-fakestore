<script setup>
import ListagemProdutos from '@/components/ListagemProdutos.vue'
import MenuSuperior from '@/components/MenuSuperior.vue'
import ToolBar from '@/components/ToolBar.vue'
</script>

<template>
  <div class="tudo">
    <div class="container">
      <ToolBar class="tool-bar" />
    </div>
    <div class="right">
      <MenuSuperior class="menu" />
      <ListagemProdutos class="produtos" />
    </div>
  </div>
</template>
<style scoped>
.tudo {
  display: grid;
  grid-template-columns: 15% 85%;
}

@media (max-width: 768px) {
  .tudo {
    grid-template-columns: 100%;
  }
}

.tool-bar {
  height: 100%;
}

.menu {
  height: 4vw;
}
.produtos {
  widows: 80%;
}
</style>
