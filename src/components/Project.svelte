<script lang='ts'>
    export let link;
    export let title = "";
    export let image = "";
    export let description = "";
    export let technologies = [];
    export let code = "";
    let hovered: Boolean = false;
    import { tweened } from 'svelte/motion';
    import { cubicOut } from 'svelte/easing';

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
        background-color: rgba(194, 189, 212, 0.13);
        // rgba(194, 189, 212, 0.418)
        &__title {
            font-weight: 400;
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
    <img class="project__img" src={image} alt="A screenshot of {title}" />
    <div class="project__description">{description}</div>
    <div class="project__footer">
        <ul>
            {#each technologies as technology}
                <li>{technology}</li>
            {/each}
        </ul>
        <a href={code}>Source Code</a>
    </div>
</div>