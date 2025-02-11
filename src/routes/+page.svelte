<script>
    function irParaCatalogoGabys() {
        window.location.href = "/pagina2";
    }

    function irParaCatalogoLendarios() {
        window.location.href = "/pagina3";
    }

    function aboutGame() {
        alert("Este é um jogo baseado no Drawing Garden. Divirta-se!");
    }
</script>

<style>
    /* Importando fontes do Google Fonts */
    @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Noto+Serif+Hentaigana:wght@200;400;700;900&display=swap');

    body {
        height: 100%;
        margin: 0;
        padding: 0;
        overflow: hidden;
        color: white;
        font-family: 'Bebas Neue', sans-serif;
    }

    .background {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: url("/imagens/teste.png") no-repeat center center fixed;
        background-size: cover;
        z-index: -1;
    }

    #container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
        width: 100%;
        z-index: 1;
        background: transparent;
    }

    h1 {
        font-size: 72px;
        color: #32CD32; /* Verde claro */
        letter-spacing: 5px;
        margin-bottom: 20px;
        font-weight: 700;
        font-family: 'Bebas Neue', sans-serif;
    }

    /* Remover o span e manter a cor verde para todo o título */
    h1 span {
        font-size: 72px;
        color: #32CD32; /* Verde claro */
    }

    /* Estilizando os botões do menu */
    .menu-option {
        font-size: 28px;
        margin: 20px;
        padding: 15px 30px;
        background: linear-gradient(145deg, #32CD32, #228B22); /* Cor verde gradiente */
        color: white;
        border-radius: 12px;
        cursor: pointer;
        font-weight: 500;
        font-family: 'Noto Serif Hentaigana', serif;
        transition: all 0.3s ease;
        border: 2px solid transparent;
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    }

    .menu-option:hover {
        background: linear-gradient(145deg, #228B22, #32CD32);
        transform: scale(1.05);
        box-shadow: 0 8px 16px rgba(0, 0, 0, 0.4);
    }

    .menu-option:active {
        transform: scale(1.02);
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    }
</style>

<div class="background"></div> <!-- Imagem de fundo -->
<div id="container">
    <!-- Título do catálogo -->
    <h1>CATALOGO DE POKEMONS</h1>
    <!-- Botões de navegação -->
    <div class="menu-option" on:click={irParaCatalogoGabys}>Pokemons Comuns</div>
    <div class="menu-option" on:click={irParaCatalogoLendarios}>Pokemons Lendários</div>
</div>