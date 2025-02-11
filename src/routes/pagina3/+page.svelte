<script>
    let cards = [
        {
            title: "Articuno ",
            image: "https://http2.mlstatic.com/carta-pokemon-lendario-articuno-e-zapdos-lote-de-100-cartas-D_NQ_NP_770089-MLB31312536462_072019-F.jpg",
            description: "Um poderoso Pokémon Lendário do tipo Gelo . Um verdadeiro clássico entre os treinadores."
        },
        {
            title: "Mewtwo GX",
            image: "https://http2.mlstatic.com/carta-pokemon-mewtwo-gx-3973-lendas-luminescentes-D_NQ_NP_709145-MLB30577098043_052019-F.jpg",
            description: "Mewtwo GX é um dos Pokémon mais icônicos, conhecido por sua força psíquica e habilidades devastadoras."
        },
        {
            title: "Lugia GX",
            image: "https://http2.mlstatic.com/carta-pokemon-lendario-ho-oh-gx-e-lugia-gx-sol-e-lua-D_NQ_NP_827091-MLB30835376112_052019-F.jpg",
            description: "Lugia, um dos lendários mais poderosos, trazendo voo para as batalhas épicas."
        },
        {
            title: "Mew",
            image: "https://th.bing.com/th/id/R.022ddc915147c2cd8ebcfe6893466a96?rik=%2bEat4mow3Mc1Xw&pid=ImgRaw&r=0",
            description: "Mew GX é um dos Pokémon mais poderosos e icônicos da franquia. Criado a partir do DNA de Mew, ele possui habilidades psíquicas devastadoras, sendo capaz de dominar batalhas com sua força impressionante."
        },
        {
    "title": "Celebi",
    "image": "https://img.mypcards.com/img/2/1251/pokemon_ssh_001_202/pokemon_ssh_001_202_pt.jpg",
    "description": "Celebi é o lendário Pokémon do tempo, guardião da floresta e capaz de viajar através de diferentes épocas."
},
        {
            title: " Lunala",
            image: "https://th.bing.com/th/id/OIP.FVTVxy4cZsiNlnL_kygG6wHaKV?rs=1&pid=ImgDetMain",
            description: "Solgaleo e Lunala são Pokémon que representam o sol e a lua, possuindo habilidades místicas impressionantes."
        }
    ];

    function baixarImagem(url, nome) {
        const link = document.createElement('a');
        link.href = url;
        link.download = nome;
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
    }

    function voltarPagina() {
        window.history.back();
    }
</script>

<style>
    body {
        margin: 0;
        padding: 0;
        font-family: 'Arial', sans-serif;
        background-color: #f4f4f4;
        color: #333;
        text-align: center;
    }

    .header {
        background-color: #dda0dd;
        padding: 20px;
        font-size: 2em;
        font-weight: bold;
        text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
        color: #000;
    }

    .catalog {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 20px;
        padding: 20px;
        max-width: 1200px;
        margin: 0 auto;
    }

    .card {
        background: white;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        overflow: hidden;
        transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        text-align: center;
    }

    .card:hover {
        transform: scale(1.05);
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    }

    .card img {
        width: 100%;
        height: 300px;
        object-fit: cover;
    }

    .card-content {
        padding: 15px;
    }

    .card-title {
        font-size: 1.5em;
        margin-bottom: 10px;
        color: #ff6600;
    }

    .card-description {
        font-size: 1em;
        color: #666;
    }

    .download-button {
        background-color: #ff00aa;
        color: white;
        padding: 10px 15px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        margin-top: 10px;
        transition: background 0.3s;
    }

    .download-button:hover {
        background-color: #ff00aa;
    }

    .back-button {
        background-color: #ff00aa;
        color: white;
        padding: 15px 25px;
        border: none;
        border-radius: 10px;
        font-size: 1.2em;
        cursor: pointer;
        margin: 30px auto;
        display: block;
        transition: background 0.3s;
    }

    .back-button:hover {
        background-color: #b52b27;
    }

    .footer {
        text-align: center;
        padding: 10px;
        background-color: #dda0dd;
        color: black;
        font-size: 1em;
        margin-top: 20px;
    }
</style>

<div class="header">Catálogo de Cartas Pokémon</div>
<div class="catalog">
    {#each cards as card}
        <div class="card">
            <img src="{card.image}" alt="{card.title}">
            <div class="card-content">
                <div class="card-title">{card.title}</div>
                <div class="card-description">{card.description}</div>
                <button class="download-button" on:click={() => baixarImagem(card.image, card.title + ".jpg")}>
                    Baixar Imagem
                </button>
            </div>
        </div>
    {/each}
</div>

<button class="back-button" on:click={voltarPagina}>Voltar</button>

<div class="footer">
    © 2025 - Catálogo de Cartas Pokémon | Feito com ❤️ para fãs.
</div>
