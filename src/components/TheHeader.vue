<template>
    <header>
        <img class="logo" src="../assets/images/logo.svg" alt="">

        <nav id="navigation">
            <div class="links">
                <span class="menu">Features <img src="../assets/icons/icon-arrow-down.svg" alt=""></span>
                <span class="menu">Company <img src="../assets/icons/icon-arrow-down.svg" alt=""></span>
                <span><a href="#">Careers</a></span>
                <span><a href="#">About</a></span>
            </div>
            
            <div class="buttons">
                <button class="button">Login</button>
                <button id="register" class="button">Register</button>
            </div>
        </nav>

        <button id="toggle">☰</button>

    </header>
</template>

<style scoped>
header {
    display: flex;
    padding: 1.2em;
}

.logo {
    height: 27px;
    margin-right: 2em;
}

#navigation {
    width: 100%;
    display: inline-grid;
    grid-template-columns: 1fr auto;
}

#navigation span {
    margin: 0 1em;
}

#navigation span img {
    margin-bottom: 3px;
}

#navigation a {
    text-decoration: none;
    color: inherit;
}

.buttons {
    justify-self: right;
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

#toggle {
    border: none;
    background-color: inherit;
    font-size: 2.5em;

    display: none;
}

#navigation *:hover, .button, #toggle {
    cursor: pointer;
    color: var(--almost-black);
}


@media screen and (width < 400px) {
  header {
    justify-content: space-between;
    position: sticky;
    top: 0;
  }

  nav, .buttons {
    display: none !important;
  }

  #toggle {
    display: inline;
  }

  #navigation.sidenav {
    display: block !important;;
    position: fixed;
    right: 0;
    top: 0;

    height: 100%;
    width: 50%;

  }
}
</style>