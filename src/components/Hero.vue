<script setup>
import Fotografo from "../assets/fotografo.png"
</script>

<template>
    <section class="hero-container">
        <div class="hero-text">
            <h1>Onde a paisagem vira <span>inspiração</span>.</h1>
            <h3>Explore paisagens, cores e luzes que inspiram novas histórias através da fotografia.</h3>
        </div>
        <img :src="Fotografo" alt="Imagem de um(a) fotográfogo.">
    </section>
</template>

<style scoped lang="scss">
@use "@/style/_variables.scss" as vars;

.hero-container {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 15.5vh 7.7vh 10.9vh 7.7vh;
    
    gap: 16vh;
    
}

.hero-text {
    display: flex;
    flex-direction: column;
    font-family: vars.$font-poppins;
    gap: 1.5vh;
    
    

    h1{
        font-size: 6vh;
        font-weight: 800;
        max-width: 10.7em;
            span{
                font-size: 8.5vh;
                color: #E1306C;
            }
    }
    h3{
        font-size: 20px;
        font-weight: 500;
        color: #262626;
        max-width: 35em;
        
    }
}
</style>