<script>
    import backgroundImage from "$lib/assets/background.jpg";
</script>
<section class="background" style="background-image: linear-gradient(
    to bottom, 
    rgba(0, 0, 0, 0), 
    rgba(119, 16, 0, 0.8)), 
    url('{backgroundImage}');">
    <nav class="navbar">
        <a class="link" href="/">El ascenso del depredador</a>
        <a class="link ml-auto" href="/about">Sobre nosotros</a>
        <a class="link" href="/play">Jugar</a>
        <button>Descargar</button>
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
    }

    .footer {
        text-align: center;
        color: antiquewhite;
        padding: 1rem 0;
        background-color: rgba(119, 16, 0, 0.8);
    }

    .ml-auto {
        margin-left: auto;
    }

    .navbar {
        display: flex;
        column-gap: 1rem;
        padding: 1.5rem;
        background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.7), rgba(0, 255, 0, 0));
        position: sticky;
    }

    .link {
        text-decoration: none;
        color: antiquewhite;
        font-weight: bold;
        font-size: 1.5rem;
    }

    .background {
        /* background-image: linear-gradient(
            to bottom, 
            rgba(0, 0, 0, 0), 
            rgba(119, 16, 0, 0.8)), 
            url('../lib/assets/background.jpg'); */
        background-size: cover;
        height: 100dvh;
    }
</style>