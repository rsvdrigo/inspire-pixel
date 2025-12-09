<script setup>
import axios from 'axios';
import { ref } from 'vue';
import Card from "./Card.vue";

const apiImgs = ref([])

async function loadingApiImgs() {
   const res = await axios.get("https://picsum.photos/v2/list?page=3&limit=12"); 
   apiImgs.value = res.data;
}
loadingApiImgs()
</script>

<template>
  <div class="main-wrapper">
    <h2 class="inspire-text">Inspire-se</h2>

    <div class="cards-grid">
       <Card
         v-for="photos in apiImgs"
         :key="photos.id"
         :image="photos.download_url"
       />
    </div>
  </div>
</template>

<style scoped lang="scss">
@use "@/style/_variables.scss" as vars;

.main-wrapper {
    max-width: 1538px;
    margin: 0 auto;
    padding: 40px 20px;
}

.inspire-text {
    font-size: 4vh;
    font-weight: 400;
    margin-bottom: 25px;
    font-family: vars.$font-poppins;
    color: #262626;
    text-align: left;
}

.cards-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

@media (max-width: 768px) {
    .main-wrapper {
        padding: 20px;
    }

    .inspire-text {
        font-size: 2.3vh;
    }

    .cards-grid {
        grid-template-columns: repeat(2, 1fr); 
        gap: 15px;

        & > :nth-child(n+7) {
            display: none;
        }
    }
}
</style>