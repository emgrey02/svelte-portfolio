<script lang='ts'>
import App from "../App.svelte";
import Bio from "./Bio.svelte";


</script>

<footer class="footer">
    <h2 class="footer__contact-title">Contact Me</h2>
    <div class="sm-links">
        <ul class="sm-links__link">
            <li>
                <a href='https://twitter.com/greyypse'>
                    <img src='./images/twitter.svg' alt="twitter logo">
                </a>
            </li>
        </ul>
        <ul class="sm-links__link">
            <li>
                <a href="https://github.com/emgrey02">
                    <img src='./images/github.svg' width='40' alt="github logo">
                </a>
            </li>
        </ul>
        <ul class="sm-links__link">
            <li>
                <a href="https://open.spotify.com/user/1223292638?si=3879996965d44679">
                    <img src='./images/spotify.svg' alt='spotify logo'>
                </a>
            </li>
        </ul>
        <ul class="sm-links__link">
            <li>
                <a href="https://linkedin.com/in/emma-grey-289321190/">
                    <img src="./images/linkedin.svg" alt="linkedin logo">
                </a>
            </li>
        </ul>
        <ul class="sm-links__link">
            <li>
                <a href="https://www.youtube.com/channel/UCyh26WCoIMLmXchQY1VZhcg">
                    <img src="./images/youtube.svg" alt="youtube logo">
                </a>
            </li>
        </ul>
    </div>
    <p>© Emma Grey</p>
</footer>

<style lang="scss">
    .footer {
        width: 100%;
        background-color: rgba(97, 97, 172, 0.507);
        position: absolute;

        &__contact-title {
            text-align: center;
            padding-top: 3rem;
            font-weight: 200;
        }
    }

    .sm-links {
        display: flex;
        justify-content: space-around;
        align-items: center;
        width: 60%;
        gap: 1rem;
        margin: auto;
        padding: 2rem;

        &__link {
            list-style: none;
            padding: 0;
        }
    }

    p {
        text-align: center;
        padding: 1rem;
    }
</style>