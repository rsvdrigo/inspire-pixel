<script setup>
 import { ref } from 'vue';
import { Icon } from '@iconify/vue';

defineProps(["image"]);

const favorite = ref(false);

const handleHeartColor = () => {
    favorite.value = !favorite.value;
}
</script>

<template>
   <div class="card">
        <button @click="handleHeartColor">            
            <Icon v-if="favorite" icon="material-symbols:favorite" class="favorite-icon favorite" />
            <Icon v-else icon="material-symbols:favorite" class="favorite-icon" />
        </button>
        <img class="image" :src="image" alt="imagem aleatoria"
        @click="handleHeartColor">
    </div>
</template>

<style scoped lang="scss">

.card {
    position: relative;
    width: 100%;
    padding-bottom: 169.5%;

    .favorite-icon {
        position: absolute;
        top: 15px;
        right: 15px;
        font-size: 30px;
        color: white;
        cursor: pointer;
        z-index: 2;
    }

    .favorite {
        color: #ff0000;
    }

    .image {
       position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 10px;
        cursor: pointer;
    }

    &:hover {
        filter: brightness(0.9);
    }
}
</style>