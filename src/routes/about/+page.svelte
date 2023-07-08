<script>
    import prof01 from "$lib/assets/prof-01.webp";
    import prof02 from "$lib/assets/prof-02.webp";
</script>

<svelte:head>
    <title>Sobre nosotros | El ascenso del Depredador</title>
</svelte:head>

<main class="about">
    <section class="about-container">
        <section>
            <img class="profile-picture" src={prof01} alt="Agustin Profile">
        </section>
        <section class="data-container">
            <h2>Agustin Espindola</h2>
            <p>Data Engineer</p>
            <a class="github-link" href="https://github.com/Espindolete">Github</a>
        </section>
    </section>

    <section class="about-container">
        <section>
            <img class="profile-picture" src={prof02} alt="Juan Profile">
        </section>
        <section class="data-container">
            <h2>Juan I. Dominguez</h2>
            <p>Web Developer</p>
            <a class="github-link" href="https://github.com/vijote">Github</a>
        </section>
    </section>
</main>

<style>
    .data-container {
        padding-top: 4rem;
        padding-left: 2rem;
    }

    .profile-picture {
        border-radius: 100%;
    }

    .github-link {
        color: bisque;
    }

    .about-container {
        display: flex;
        flex-wrap: wrap;
        column-gap: 2rem;
        color: antiquewhite;
    }

    .about {
        padding: 2rem;
        display: flex;
        gap: 12rem;
        flex-wrap: wrap;
    }
</style>