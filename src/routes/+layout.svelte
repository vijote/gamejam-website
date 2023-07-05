<script>
    import backgroundImage from "$lib/assets/background.jpg";
</script>
<section class="background" style="background-image: linear-gradient(
    to bottom, 
    rgba(0, 0, 0, 0), 
    rgba(119, 16, 0, 0.8)), 
    url('{backgroundImage}');">
    <nav class="navbar">
        <a class="link name" href="/">El ascenso del depredador</a>
        <a class="link ml-auto" href="/about">Sobre nosotros</a>
        <a class="link" href="/play">Jugar</a>
        <button class="download-button">Descargar</button>
    </nav>
    
    <slot/>
</section>

<footer class="footer">
    Desarrollado para Chaco Futura 2023 - JADEv
</footer>

<style>
    :global(html) {
        margin: 0;
        padding: 0;
        background-color: #0f0f0f;
    }

    :global(body) {
        margin: 0;
        font-family: sans-serif;
        background-color: rgba(119, 16, 0, 0.8);
    }

    .footer {
        text-align: center;
        color: antiquewhite;
        padding: 1rem 0;
    }

    .ml-auto {
        margin-left: auto;
    }

    .navbar {
        display: flex;
        column-gap: 1rem;
        padding: 1rem 1.5rem;
        align-items: center;
        background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.7), rgba(0, 255, 0, 0));
        position: sticky;
    }

    .link {
        text-decoration: none;
        color: antiquewhite;
        font-weight: bold;
        font-size: 1.25rem;
        width: fit-content;
    }

    .name {
        font-size: 1.5rem;
    }

    .download-button {
        all: unset;
        cursor: pointer;
        background-color: rgb(154, 31, 0);
        padding: 0.35rem 1rem;
        font-weight: bold;
        font-size: 1.25rem;
        border-radius: 0.25rem;
        color: white;
    }

    .download-button:focus {
        outline: white 5px auto;
    }

    .background {
        /* background-image: linear-gradient(
            to bottom, 
            rgba(0, 0, 0, 0), 
            rgba(119, 16, 0, 0.8)), 
            url('../lib/assets/background.jpg'); */
        background-size: cover;
        min-height: 100svh;
    }
</style>