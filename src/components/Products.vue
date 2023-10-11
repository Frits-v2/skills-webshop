<script setup lang="ts">
import { NButton} from 'naive-ui';
import dataset from '@/assets/dataset.json';
defineProps<{
  msg: string
}>()
</script>

<template>
  <div class="card-container">
    <n-card v-for="product in dataset.products" :key="product.id">
      <div class="title-name">{{ product.name }}<br /></div>
      

        <img :src="'/public/products/' + product.name + '.png'" width="200">
      <h3>
        <div class="info-card">Prijs: ${{ product.price }}<br /></div>
        <div id="Mybutton">
          <n-button strong secondary round type="info">
          Info
          </n-button>
        </div>
   
        
      </h3>
    </n-card>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.card-container {
  display: flex;
  gap: 50%; /* Adjust the gap between cards as needed */

  
}

.n-card {
  max-width: 300px;
  border:solid; 
  border:solid,white;
  display: flex;
  justify-content: center;
  align-items: center;
}
.title-name{
  Font-weight:bold;
  font-size:25px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.info-card{
  display: flex;
  justify-content: center;
  align-items: center;
}
#Mybutton{
  display: flex;
  justify-content: center;
  align-items: center;
}


@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
