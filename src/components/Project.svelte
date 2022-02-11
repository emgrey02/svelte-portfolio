<script lang='ts'>
    import { tweened } from 'svelte/motion';
    import { cubicOut } from 'svelte/easing';
    export let link: string;
    export let title: string;
    export let image: string;
    export let description: string;
    export let technologies: string[] = [];
    export let code: string;
    let hovered: Boolean = false;

    const shadow = tweened(0, { duration: 500, easing: cubicOut});

    function handleMouseEnter() {
        shadow.set(1);
        hovered = true;
    }

    function handleMouseLeave() {
        shadow.set(0);
        hovered = false;
    }

</script>

<style type="text/scss">
    .project {
        text-align: center;
        margin: 1rem;
        padding: 2rem;
        border-radius: .2rem;
        background-color: rgb(236, 234, 243);
        // rgba(194, 189, 212, 0.418)
        &__title {
            font-weight: 500;
            font-size: 1.8rem;
            padding: 1.5rem;
            margin: 1rem auto;
        }

        &__img {
            width: 100%;
            max-width: 400px;
            height: auto;
            padding: 2rem 2rem 1rem;
        }

        &__description {
            font-size: 15px;
            padding: .5rem 1rem;
            line-height: 1.5;
            text-align: left;
            margin-bottom: 2rem;
        }

        &__footer {
            ul {
                list-style: none;
                display: flex;
                flex-wrap: wrap;
                gap: 1rem;
                padding-left: 0;
                text-transform: uppercase;
                justify-content: center;
            }
        }

    }

    @media (min-width: 1200px) {
        .project {
            
        }
    }
</style>

<div 
    on:mouseenter={handleMouseEnter}
    on:touchstart={handleMouseEnter}
    on:mouseleave={handleMouseLeave}
    on:touchend={handleMouseLeave}
    style="box-shadow: {$shadow * -15}px {$shadow * -5}px #e1b1cC, {$shadow * 10}px {$shadow * 10}px #E5E3ED, {$shadow * 25}px {$shadow * 15}px #8257a3;"
    class="project">
    <h2 class="project__title">
        <a href={link}>{title}</a>
    </h2>
    <hr>
    <img class="project__img" src={image} alt="A screenshot of {title}" />
    <div class="project__description">{description}</div>
    <hr>
    <div class="project__footer">
        <ul>
            {#each technologies as technology}
                <li>{technology}</li>
            {/each}
        </ul>
        <a href={code}>Source Code</a>
    </div>
</div>