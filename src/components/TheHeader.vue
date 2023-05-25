<template>
    <header>
        <img class="logo" src="../assets/images/logo.svg" alt="">

        <nav id="navigation">
            <span class="menu">Features <img src="../assets/icons/icon-arrow-down.svg" alt=""></span>
            <span class="menu">Company <img src="../assets/icons/icon-arrow-down.svg" alt=""></span>
            <span><a href="#">Careers</a></span>
            <span><a href="#">About</a></span>
        </nav>

        <div class="buttons">
            <button class="button">Login</button>
            <button id="register" class="button">Register</button>
        </div>
    </header>
</template>

<style scoped>
header {
    padding: 1.2em;
    display: grid;
    grid-template-columns: auto 1fr auto;
    align-items: center;
}

.logo {
    margin-right: 2em;
}

#navigation {
    justify-self: left;
}

#navigation span {
    margin: 0 1em;
    color: var(--medium-gray);
}

#navigation span img {
    margin-bottom: 3px;
}

#navigation a {
    text-decoration: none;
    color: inherit;
}

.button {
    display: inline;
    margin: 0 .4em;
    font-family: inherit;

    background-color: inherit;
    border: none;
    border-radius: 12px;
    padding: .8em 1.3em;
}

#register {
    border: 1px solid var(--almost-black);
}

#navigation *:hover, .button {
    cursor: pointer;
    color: var(--almost-black);
}
</style>