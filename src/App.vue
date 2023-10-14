<script setup lang="ts">
import { ref, reactive, computed } from 'vue'
let product = reactive({
  image: true
})

const icon = ref('/360.svg')

const changeState = () => {
  product.image = !product.image
  icon.value = icon.value === '/360.svg' ? '/close.svg' : '/360.svg'
}

const productImage = computed(() => {
  return product.image ? '/sofa.svg' : '/sofa.gif'
})
</script>

<template>
  <section id="products-page">
    <div id="left-side">
      <div class="image">
        <img :src="productImage" alt="" srcset="">
        <img :src="icon" @click="changeState" alt="" srcset="">
      </div>
    </div>
    <div id="right-side">
      <div class="content">
        <p>CÓDIGO: 42404</p>
        <h1>Sofá Margot II - Rosé</h1>
        <p>R$ 4.000</p>
        <button>ADICIONAR À CESTA</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
#products-page {
  font-family: 'Lato', sans-serif;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  height: 100vh;
  background-color: #D9CDF7;
}

#left-side {
  /* background-color: red; */
  display: flex;
  justify-content: flex-end;
  place-items: center;
}

#left-side .image {
  position: relative;
}

#left-side .image img:first-child {
  width: 449px;
}

#left-side .image img:last-child {
  position: absolute;
  top: 0;
  right: 0;
}

#right-side {
  /* background-color: blue; */
  display: flex;
  place-items: center;
}

#right-side .content p {
  color: #271A45;
}

#right-side .content p:first-child {
  font-size: 10px;
  font-weight: 300;
}

#right-side .content p:last-child {
  font-size: 16px;
  font-weight: 400;
}

#right-side .content h1 {
  margin: 12px 0;
  font-family: 'Crimson Pro', serif;
  font-size: 32px;
  font-weight: 600;
}

#right-side .content button {
  margin-top: 20px;
  border: 0.5px solid #271A45;
  border-radius: 999px;
  padding: 8px 16px;
  background-color: transparent;
}
</style>
