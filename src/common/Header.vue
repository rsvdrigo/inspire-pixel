<script setup>
import { Icon } from '@iconify/vue';
import logoInspire from "../assets/logoInspire.png"


</script>

<template>
    <header>
        <img :src="logoInspire" alt="Imagem do Logo da inspire pixel">
        <div class="navbar-manu">
            <nav>
                <Icon class="search-icon nav-icon" icon="material-symbols:search" width="40" />
                <a href="#">Início</a>
                <a href="#">Galeria</a>
                <a href="#">Favoritos</a>
                <Icon class="user-icon nav-icon" icon="material-symbols:person" width="40" />

            </nav>
        </div>
    </header>
</template>

<style scoped lang="scss">
@use "@/style/_variables.scss" as vars;


header{
    display:flex;
    justify-content: space-between;
    padding: 4.2vh 7.6vh 4.2vh 7.7vh;
    align-items: center;
}
nav{
    display: flex;
    align-items: center;
    gap: 6.4vh;
    font-family: vars.$font-poppins;
}

</style>