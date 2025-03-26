<script>
</script>

<nav>
    <a href="/" id="home-link">DiveToTheCore</a>

    <ul role="menu">
        <li role="none"><a role="menuitem" href="/about">Sobre nós</a></li>
        <li role="none">
            <a role="menuitem" href="https://github.com/Jonyski/DiveToTheCore">
                Nos dê me uma estrela
            </a>
        </li>
    </ul>
</nav>

<style>
    nav {
        display: flex;
        background-color: var(--secondary-color-bg);
        justify-content: space-between;
        align-items: center;
        padding: 0.5rem 3rem;

        a {
            font-size: 2rem;
            text-decoration: none;
            color: var(--primary-color-font);
        }

        ul[role="menu"] {
            list-style: none;
            display: flex;
            gap: 4rem;
        }
    }
</style>
