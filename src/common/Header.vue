<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
import logoInspire from "../assets/logoInspire.png"

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
}
</script>

<template>
    <header>
        <img :src="logoInspire" alt="Imagem do Logo da inspire pixel" class="logo">

        <nav class="desktop-nav">
            <Icon class="nav-icon search-icon" icon="material-symbols:search" width="28" />
            <div class="links">
                <a href="#">Início</a>
                <a href="#">Galeria</a>
                <a href="#">Favoritos</a>
            </div>
            <Icon class="nav-icon user-icon" icon="material-symbols:person-outline" width="32" />
        </nav>

        <div class="mobile-controls">
             <Icon class="nav-icon search-icon" icon="material-symbols:search" width="28" />
            
            <button @click="toggleMenu" class="hamburger-btn">
                <Icon 
                    :icon="isMenuOpen ? 'material-symbols:close' : 'material-symbols:menu'" 
                    width="35" 
                />
            </button>
        </div>

        <div class="mobile-menu" :class="{ 'open': isMenuOpen }">
            <a href="#">Início</a>
            <a href="#">Galeria</a>
            <a href="#">Favoritos</a>
        </div>
    </header>
</template>

<style scoped lang="scss">
@use "@/style/_variables.scss" as vars;


$pink-color: #E1306C;
$text-color: #262626;

header {
    display: flex;
    justify-content: space-between;
    padding: 20px 8%; 
    align-items: center;
    background-color: #fff;
    position: relative; 
    font-family: vars.$font-poppins;
}

.logo {
    height: 40px; 
}

.desktop-nav {
    display: flex;
    align-items: center;
    gap: 40px;

    .links {
        display: flex;
        gap: 40px;
        
        a {
            text-decoration: none;
            color: $text-color;
            font-weight: 500;
            font-size: 1rem;
            
            &:hover {
                color: $pink-color;
            }
        }
    }

    .nav-icon {
        cursor: pointer;
        color: $text-color;
    }

 
    .user-icon {
        color: $pink-color; 
    }
}


.mobile-controls {
    display: none; 
    align-items: center;
    gap: 20px;

    .search-icon {
        color: $text-color;
    }

    .hamburger-btn {
        background: none;
        border: none;
        cursor: pointer;
        display: flex;
        align-items: center;
        
        
        color: $pink-color; 
    }
}


.mobile-menu {
    display: none; 
    position: absolute;
    top: 100%; 
    left: 0;
    width: 100%;
    background-color: white;
    flex-direction: column;
    padding: 20px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    z-index: 10;
    gap: 20px;
    text-align: center;

    a {
        text-decoration: none;
        color: $text-color;
        font-weight: 500;
        font-size: 1.1rem;
        padding: 10px;
        border-bottom: 1px solid #f0f0f0;
        
        &:hover {
            color: $pink-color;
        }
    }

    .mobile-user {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 10px;
        color: $pink-color;
        font-weight: 600;
    }
}


@media (max-width: 900px) {
    
    .desktop-nav {
        display: none;
    }

    
    .mobile-controls {
        display: flex;
    }

    
    .mobile-menu {
        
        &.open {
            display: flex;
        }
    }
}
</style>