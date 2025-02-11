<script>
    let cards = [
        {
            title: "Dragonite GX",
            image: "https://http2.mlstatic.com/carta-pokemon-dragonite-gx-com-lote-100-cartas-originais-D_NQ_NP_641035-MLB29674038342_032019-F.jpg",
            description: "Dragonite GX é um poderoso Pokémon do tipo Dragão, conhecido por sua força e ataques devastadores."
        },
        {
            title: "Solgaleo GX",
            image: "https://th.bing.com/th/id/OIP.4ITz0gt3Bu4MfMOrciU7GwHaKV?rs=1&pid=ImgDetMain",
            description: "Solgaleo GX é um Pokémon lendário do tipo Metálico e Psíquico. Possui ataques incríveis."
        },
        {
            title: "Lunala GX",
            image: "https://th.bing.com/th/id/OIP.Qycm9jnTUHexOqvIwB0VrwHaKV?rs=1&pid=ImgDetMain",
            description: "Lunala GX é um Pokémon lendário do tipo Psíquico. Sua elegância e poder fazem dela uma carta valiosa."
        },
        {
            title: "Mewtwo GX",
            image: "https://th.bing.com/th/id/OIP.BsiqvvqwNw33f19mZW9ZZQAAAA?rs=1&pid=ImgDetMain",
            description: "Mewtwo GX é um dos Pokémon mais icônicos do universo Pokémon. Seus ataques psíquicos são devastadores."
        },
        {
            title: "Solosis",
            image: "https://images.wikidexcdn.net/mwuploads/wikidex/thumb/a/a8/latest/20221202172744/Solosis_(Tempestad_Plateada_TCG).png/250px-Solosis_(Tempestad_Plateada_TCG).png",
            description: "Solosis é um Pokémon adorável do tipo Psíquico. Embora pequeno, ele pode ser muito útil em batalhas."
        },
        {
            title: "Incineroar GX",
            image: "https://http2.mlstatic.com/carta-pokemon-incineroar-gx-97181-unio-de-aliados-D_NQ_NP_945957-MLB29698400634_032019-F.jpg",
            description: "Incineroar GX é um Pokémon do tipo Fogo com habilidades que causam grandes danos aos oponentes."
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
