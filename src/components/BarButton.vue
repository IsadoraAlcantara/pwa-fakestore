<script setup>
import HomeOutline from 'vue-material-design-icons/HomeOutline.vue'
import CartOutline from 'vue-material-design-icons/CartOutline.vue'
import AccountOutline from 'vue-material-design-icons/AccountOutline.vue'
import InformationOutline from 'vue-material-design-icons/InformationOutline.vue'
</script>
<template>
    <div class="bar-button">
        <HomeOutline class="icon" size="32px"/>
        <CartOutline class="icon" size="32px" />
        <AccountOutline class="icon" size="32px" />
        <InformationOutline class="icon" size="32px" />
    </div>
</template>
<style>
.bar-button {
    height: 20vw;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    color: #797E8C;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 17vw;
    position: fixed;
    bottom: 0;
    background-color: white;
    width: 100%;
}

.icon:hover {
    color: #5155a6;
}

</style>    