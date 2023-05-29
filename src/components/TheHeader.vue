<script setup>
import { ref } from 'vue';

const sidenav = ref(false)
function toggleSidenav() {
    sidenav.value = !sidenav.value
}
</script>

<template>
    <header>
        <img class="logo" src="../assets/images/logo.svg" alt="">

        <nav id="navigation" :class="{sidenav}">
            <div class="links">
                <span>
                    Features
                    <img src="../assets/icons/icon-arrow-down.svg" alt="">

                    <div class="menu">
                        <ul>
                            <li>
                                <img src="../assets/icons/icon-todo.svg" alt="">
                                <p>Todo List</p>
                            </li>
                            <li>
                                <img src="../assets/icons/icon-calendar.svg" alt="">
                                <p>Calendar</p>
                            </li>
                            <li>
                                <img src="../assets/icons/icon-reminders.svg" alt="">
                                <p>Reminders</p>
                            </li>
                            <li>
                                <img src="../assets/icons/icon-planning.svg" alt="">
                                <p>Planing</p>
                            </li>
                        </ul>
                    </div>
                </span>
                <span>
                    Company
                    <img src="../assets/icons/icon-arrow-down.svg" alt="">
                    
                    <div class="menu company">
                        <ul>
                            <li>
                                <p>History</p>
                            </li>
                            <li>
                                <p>Our team</p>
                            </li>
                            <li>
                                <p>Blog</p>
                            </li>
                        </ul>
                    </div>
                </span>
                <span><a href="#">Careers</a></span>
                <span><a href="#">About</a></span>
            </div>
            
            <div class="buttons">
                <button class="button">Login</button>
                <button id="register" class="button">Register</button>
            </div>
        </nav>

        <button id="toggle" @click="toggleSidenav">{{ sidenav ? "🞨" : "☰" }}</button>

    </header>
</template>

<style scoped>
header {
    display: flex;
    align-items: center;
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
    align-items: center;
}

#navigation span {
    position: relative;
    margin: 0 1em;
}

#navigation span img {
    margin-bottom: 3px;
}

#navigation a {
    text-decoration: none;
    color: inherit;
}

#navigation * {
    transition: color .4s ease, max-height 1s, visibility 1s;
}

.menu {
    width: 7em;
    max-height: 1px;
    visibility: hidden;
    overflow: hidden;
    background-color: var(--almost-white);
    color: var(--medium-gray);

    position: absolute;
    top: 2em;

    padding: 1em;
    border-radius: 15px;
    box-shadow: 1px 1px 50px 1px var(--medium-gray);
}

span:hover .menu {
    max-height: 200px;
    visibility: visible;
}

/*This is a hack tbh but i'm tired and it works for now */
.menu.company {
    left: 50%
}

.menu p {
    display: inline;
    margin-left: .7em;
}

.menu p:hover {
    color: var(--almost-black)
}

.menu ul {
    list-style: none;
    padding: 0;
    margin: 0;
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
    padding: 0;
    border: none;
    background-color: inherit;
    font-size: 2.5em;

    display: none;
    z-index: 1;
}

#navigation span:hover, .button, #toggle {
    cursor: pointer;
    color: var(--almost-black);
}


@media screen and (width < 420px) {
  header {
    padding: 0;
    justify-content: space-between;
    position: sticky;
    top: 0;
    background-color: var(--almost-white);
  }

  nav {
    display: none !important;
  }

  #toggle {
    display: inline;
  }

  #navigation.sidenav {
    display: grid !important;
    grid-template-columns: 1fr;
    grid-template-rows: auto auto 1fr;
    row-gap: 1em;

    position: fixed;
    right: 0;
    top: 0;

    background-color: var(--almost-white);
    height: 100%;
    width: 65%;
  }

  .sidenav .links {
    grid-row: 1;
    margin-top: 3em;
    height: fit-content;

    display: grid;
    grid-template-rows: repeat(4, auto);
    row-gap: 2em;
  }

  .sidenav .menu {
    position: static;
    margin-top: 1em;
    box-shadow: none;
  }

  .sidenav .buttons {
    grid-row: 2;

    box-sizing: border-box;
    width: 100%;
    padding: 0 12%;
  }

  .sidenav .button {
    display: block;
    width: 100%;
    margin: .5em 0;
  }
}
</style>