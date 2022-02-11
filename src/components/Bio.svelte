<script lang='ts'>
    import { slide } from 'svelte/transition'
    let visible: Boolean = false;
</script>

<style lang='scss'>
    .bio {
        width: 100%;
        text-align: center;

        &__container {
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 1rem;
        }
        
        &__name {
            color: #444;
            width: min-width;
            text-transform: uppercase;
            font-size: 4em;
            font-weight: 700;
            display: inline-block;
            padding-top: 0;
            margin: 0;
        }
        
        &__button {
            margin: 0;
            margin-left: 1rem;
            padding: 0;
            border: none;
            background-color: inherit;
            font-size: 3em;
            cursor: pointer;
            color: rgb(97, 97, 172);

            &:hover, &:focus {
                outline: 2px dotted black;
            }
        }
    }

    .about {
        background-color: rgb(236, 234, 243);
        border-radius: .2rem;
        width: auto;
        height: auto;
        text-align: left;
        display: block;
        margin: auto;
        padding: 1rem 2rem;
        color: #000;

        h2 {
            text-transform: capitalize;
            margin-top: 1rem;
            margin-bottom: .2em;
            font-weight: 300;
        }
    }

    @media (min-width: 600px) {
        .about {
            width: 500px;
        }
    }
</style>

<div class="bio">
    <span class="bio__container">
        <h1 class="bio__name">Emma Grey</h1>
        <button class="bio__button" on:click={() => (visible = !visible)}>{visible ? '✖' : '▼'}</button>
    </span>
    {#if visible}
        <div class="about" transition:slide>
            <h2>About Me</h2>
            <p class="about__intro">Hello! I like to write code that exists on the web. Creating beautiful and interactive experiences for everyone is my goal. I live in New Jersey and desperately want to move somewhere warm.  In the meantime I'm in my room with a space heater, coding away.  </p>
        </div>
    {/if}
</div>