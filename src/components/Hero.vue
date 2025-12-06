<script setup>
import Fotografo from "../assets/fotografo.png"
</script>

<template>
    <section class="hero-container">
        <div class="hero-text">
            <h1>Onde a paisagem vira <span>inspiração</span>.</h1>
            <h3>Explore paisagens, cores e luzes que inspiram novas histórias através da fotografia.</h3>
        </div>
        <img class="hero-img" :src="Fotografo" alt="Imagem de um(a) fotógrafo(a).">
    </section>
</template>

<style scoped lang="scss">
@use "@/style/_variables.scss" as vars;

.hero-container {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 15.5vh 7.7vh 10.9vh 7.7vh;
    gap: 45vh;
}

.hero-text {
    display: flex;
    flex-direction: column;
    font-family: vars.$font-poppins;
    gap: 1.5vh;
    
    h1 {
        font-size: 6vh;
        font-weight: 800;
        max-width: 10.7em; 
        
        span {
            font-size: 8.5vh;
            color: #E1306C;
        }
    }

    h3 {
        font-size: 20px;
        font-weight: 500;
        color: #262626;
        max-width: 35em; 
    }
}

.hero-img {
    max-width: 50%; 
    height: auto;
}

@media (max-width: 900px) {
    .hero-container {
        flex-direction: column-reverse; 
        padding: 5vh 5%; 
        gap: 3vh; 
        text-align: center; 
    }

    .hero-text {
        width: 100%; 
        align-items: center; 

        h1 {
            font-size: 4vh; 
            max-width: 100%; 
            line-height: 1.2;

            span {
                font-size: 5vh; 
            }
        }

        h3 {
            font-size: 1.8vh; 
            max-width: 90%; 
        }
    }

    .hero-img {
        max-width: 100%; 
        width: 90%; 
        border-radius: 40px; 
        box-shadow: 0 10px 20px rgba(0,0,0,0.1); 
    }
}
</style>