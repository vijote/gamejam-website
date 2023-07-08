<script>
    import landing01 from "$lib/assets/landing-01.webp";
    import landing02 from "$lib/assets/landing-02.webp";
</script>

<svelte:head>
    <title>Inicio | El ascenso del Depredador</title>
</svelte:head>

<div class="container">
    <section class="section-container">
        <section class="section-01">
            <h2 class="game-title">Una experiencia Eat'em all</h2>
            <p class="game-description">
                Tenés lo necesario para superar a tus depredadores y volverte el mas apto para evolucionar?
            </p>
            <a class="download-button" href="https://github.com/vijote/eadd-build/archive/refs/heads/main.zip">
                Descargar
            </a>
        </section>

        <section class="section-01">
            <img class="landing-01" src={landing01} width="640" height="400" alt="Game" />
        </section>
    </section>

    <section class="section-container">
        <section class="section-01 order-sm-2">
            <img class="landing-01 glow" src={landing02} width="640" height="400" alt="Game" />
        </section>
        <section class="section-01 order-sm-1">
            <h2 class="game-title">Un desarrollo local</h2>
            <p class="game-description">
                Desarrollamos este juego en la competencia Chaco Futura 2023, este es el resultado! Esperamos lo disfrutes
            </p>
        </section>
    </section>
</div>

<style>
    @media screen and (min-width: 768px) and (orientation: landscape) {
        .section-container {
            flex-direction: row;
        }
    }

    /* Styles for mobile vertical */
    @media screen and (max-width: 767px) and (orientation: portrait) {
        .section-container {
            flex-direction: column;
        }

        .order-sm-2 {
            order: 2;
        }

        .order-sm-1 {
            order: 1;
        }
    }

    .container {
        margin: 0 auto;
        padding: 1.5rem;
    }

    .section-container {
        display: flex;
        column-gap: 2rem;
        color: antiquewhite;
    }

    .download-button {
        all: unset;
        cursor: pointer;
        background-color: rgb(249, 155, 33);
        padding: 0.35rem 1rem;
        font-weight: bold;
        font-size: 1.25rem;
        border-radius: 0.25rem;
        color: #161616;
        margin-top: 1.5rem;
        width: min-content;
        margin-left: auto;
        margin-right: auto;
    }

    .download-button:focus {
        outline: white 5px auto;
    }

    .section-01 {
        flex: 1;
        text-align: center;
        margin-bottom: 3rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .landing-01 {
        object-fit: cover;
        border-radius: 5px;
        width: 100%;
        position: relative;
        max-height: 40svh;
    }

    .game-title {
        font-size: 24px;
        margin: 20px 0;
        margin-top: 0;
    }

    .game-description {
        font-size: 18px;
        line-height: 1.5;
    }
</style>
