<script>
    import landing01 from "$lib/assets/landing-01.jpg";
</script>

<div class="container">
    <section class="section-container">
        <section class="section-01">
            <h2 class="game-title">Awesome Game Title</h2>
            <p class="game-description">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam lacinia
                auctor justo, vitae tempus lectus facilisis sed. Vestibulum sodales
                mauris sit amet mauris lacinia, vel lobortis odio pellentesque.
                Curabitur semper ligula id malesuada tincidunt.
            </p>
        </section>

        <section class="section-01">
            <img class="landing-01 glow" src={landing01} alt="Game" />
        </section>
    </section>
</div>

<style>
    .container {
        margin: 0 auto;
        padding: 1.5rem;
    }

    .section-container {
        display: flex;
        column-gap: 2rem;
    }

    .section-01 {
        flex: 1;
    }

    .landing-01 {
        object-fit: cover;
        border-radius: 5px;
        width: 100%;
        position: relative;
    }

    .game-title {
        font-size: 24px;
        margin: 20px 0;
    }

    .game-description {
        font-size: 18px;
        line-height: 1.5;
    }

    .glow::after {
        content: "";
        position: absolute;
        top: -5px;
        left: -5px;
        right: -5px;
        bottom: -5px;
        border-radius: 5px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.5); /* Adjust the shadow color and size as needed */
    }
</style>
