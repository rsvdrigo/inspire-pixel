# 📸 Inspire Pixel

**Inspire Pixel** é uma aplicação web de galeria de fotos imersiva, desenvolvida para explorar o poder do **Vue 3** com o ecossistema **Vite**. O projeto consome uma API externa para fornecer um feed de inspiração visual, combinando design responsivo, interatividade e performance.

---

## 🚀 Sobre o Projeto

O **Inspire Pixel** foi criado com o objetivo de servir como uma fonte de inspiração visual ("Onde a paisagem vira inspiração"). A aplicação apresenta uma interface limpa onde utilizadores podem navegar por uma galeria de imagens de alta qualidade, gerada dinamicamente, e interagir com o conteúdo.

### 🌟 Destaques
- **Performance:** Construído sobre o Vite para carregamento instantâneo.
- **Design Responsivo:** Layout adaptável para desktop e dispositivos móveis (menu hambúrguer e grid flexível).
- **Dados Dinâmicos:** Integração com a API Lorem Picsum para imagens aleatórias.

---

## 🛠️ Tecnologias Utilizadas

O projeto utiliza uma stack moderna de desenvolvimento web:

- **[Vue.js 3](https://vuejs.org/)** (Composition API `<script setup>`) - O coração reativo da aplicação.
- **[Vite](https://vitejs.dev/)** - Ferramenta de build e servidor de desenvolvimento ultra-rápido.
- **[Sass (SCSS)](https://sass-lang.com/)** - Pré-processador CSS para estilização modular e variáveis globais.
- **[Axios](https://axios-http.com/)** - Cliente HTTP baseado em Promises para requisições à API.
- **[Iconify](https://iconify.design/)** - Biblioteca de ícones (Material Symbols, MDI) para elementos visuais leves.
- **Vue Router** - Configurado nas dependências para gestão futura de rotas.

---

## ✨ Funcionalidades

### 1. 🖼️ Galeria de Inspiração (`InspireMenu.vue`)
- Consome a API **Lorem Picsum** (`https://picsum.photos/v2/list`).
- Exibe automaticamente uma grelha de 12 imagens curadas (Página 3 da API).
- Layout em Grid que se ajusta de 4 colunas (Desktop) para 2 colunas (Mobile).

### 2. ❤️ Interatividade dos Cards (`Card.vue`)
- Cada imagem possui um botão de "Favorito" (Coração).
- **Estado Local:** O utilizador pode clicar para alternar o estado do ícone entre contorno (não favorito) e preenchido a vermelho (favorito).
- Efeito de *hover* nas imagens para melhor feedback visual.

### 3. 📱 Navegação Responsiva (`Header.vue`)
- **Desktop:** Menu de navegação completo com ícones de pesquisa e utilizador.
- **Mobile:** Menu colapsável controlado por um botão "Hambúrguer". O menu desliza suavemente e sobrepõe o conteúdo quando ativado.

### 4. 📢 Rodapé Informativo (`Footer.vue`)
- Secção completa com links institucionais (Contato, Sobre).
- Formulário de subscrição de Newsletter.
- Ícones de redes sociais com efeitos de hover.

---

## 📂 Estrutura de Ficheiros

A organização do código segue as melhores práticas de modularização do Vue:

```text
inspire-pixel/
├── public/              # Ficheiros estáticos (ex: favicon)
├── src/
│   ├── assets/          # Imagens locais (Logótipo, Banner Hero)
│   ├── common/          # Componentes globais de layout
│   │   ├── Footer.vue   # Componente de Rodapé
│   │   └── Header.vue   # Componente de Cabeçalho e Navegação
│   ├── components/      # Componentes específicos de funcionalidades
│   │   ├── Card.vue     # Card individual da imagem (Lógica de Like)
│   │   ├── Hero.vue     # Secção de destaque (Banner principal)
│   │   └── InspireMenu.vue # Contentor da grelha de imagens (Chamada API)
│   ├── style/           # Arquitetura CSS (Sass)
│   │   ├── _main.scss     # Importação de fontes (Poppins) e layout base
│   │   ├── _reset.scss    # Reset CSS global
│   │   ├── _variables.scss # Variáveis de cores e fontes
│   │   └── index.scss     # Ponto de entrada dos estilos
│   ├── App.vue          # Componente Raiz (Orquestrador)
│   └── main.js          # Inicialização da aplicação Vue
├── index.html           # Entry point HTML
├── package.json         # Gestão de dependências e scripts
└── vite.config.js       # Configuração do Vite (Alias '@' para src)
