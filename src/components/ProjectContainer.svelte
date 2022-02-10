<div class="container">
    <slot></slot>
</div>

<style>
    .container {
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: auto;
        width: 100%;
        padding: 1rem;
        gap: 3rem;
    }

    @media (min-width: 800px) {
        .container {
            grid-template-columns: repeat(2, 1fr);
            gap: 3rem;
        }
    }

    @media (min-width: 1200px) {
        .container {
            grid-template-columns: repeat(3, 1fr);
        }
    }

    @media (min-width: 1800px) {
        .container {
            padding: 10rem;
        }
    }
</style>