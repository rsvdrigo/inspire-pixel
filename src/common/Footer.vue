<script setup>
import { Icon } from '@iconify/vue';
</script>

<template>
    <footer class="footer">
        <div class="footer-content">

            <div class="left-links">
                <div class="column">
                    <h3>Contato</h3>
                    <p>contato@inspiralens.com</p>
                    <p>Central de ajuda</p>
                    <p>Rio de Janeiro - Brasil</p>
                </div>

                <div class="column">
                    <h3>Sobre</h3>
                    <p>Políticas</p>
                    <p>Políticas de privacidade</p>
                    <p>Blog</p>
                </div>
            </div>

            <div class="column newsletter">
                <h3>Assine nossa newsletter</h3>
                <form class="newsletter-form">
                    <input type="email" placeholder="Seu email" />
                    <button type="button">Inscrever-se</button>
                </form>
            </div>

        </div>

        <div class="social-icons">
            <Icon icon="mdi:facebook" width="30" />
            <Icon icon="mdi:linkedin" width="30" />
            <Icon icon="mdi:instagram" width="30" />
            <Icon icon="mdi:twitter" width="30" />
        </div>
    </footer>
</template>

<style scoped lang="scss">
@use "@/style/_variables.scss" as vars;

.footer {
    font-family: vars.$font-poppins;
    padding: 50px 8%;
    background-color: #fff;
    display: flex;
    flex-direction: column;
    gap: 80px;
}

.footer-content {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap;
}

.left-links {
    display: flex;
    gap: 80px;
}

.column {
    display: flex;
    flex-direction: column;
    gap: 15px;

    h3 {
        font-size: 2.4vh;
        font-weight: 600;
        color: #262626;
    }

    p {
        font-size: 1.6vh;
        color: #000000;
        font-weight: 400;
        cursor: pointer;
        transition: color 0.2s;

        &:hover {
            color: #E1306C;
        }
    }
}

.newsletter {
    min-width: 300px;

    .newsletter-form {
        display: flex;
        flex-direction: column;
        gap: 15px;

        input {
            padding: 12px 15px;
            border: none;
            background-color: #F8F8F8;
            border-radius: 4px;
            font-family: 'Poppins', sans-serif;
            width: 100%;

            &::placeholder {
                color: #A0A0A0;
            }
        }

        button {
            background-color: #E1306C;
            color: white;
            border: none;
            padding: 12px 25px;
            font-weight: 600;
            border-radius: 4px;
            cursor: pointer;
            width: fit-content;
            font-family: 'Poppins', sans-serif;
            transition: background 0.3s;

            &:hover {
                background-color: #E1309C;
            }
        }
    }
}

.social-icons {
    display: flex;
    justify-content: center;
    gap: 20px;
    color: #262626;

    svg {
        cursor: pointer;
        transition: transform 0.2s;

        &:hover {
            transform: scale(1.1);
            color: #E1306C;
        }
    }
}

@media (max-width: 900px) {
    .footer-content {
        flex-direction: column;
        align-items: center;
        gap: 60px;
    }


    .newsletter {
        order: -1;
        width: 100%;
        align-items: center;
        text-align: center;

        .newsletter-form {
            align-items: center;
            width: 100%;

            input {
                text-align: center;
            }
        }
    }


    .left-links {
        flex-direction: column;
        gap: 40px;
        align-items: center;
        width: 100%;
    }


    .column {
        align-items: center;
        text-align: center;
    }
}
</style>