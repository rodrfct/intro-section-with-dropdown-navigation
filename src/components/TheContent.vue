<script setup>
import { computed, onMounted, onUnmounted, ref } from 'vue';
import HeroDesktop from '../assets/images/image-hero-desktop.png'
import HeroMobile from '../assets/images/image-hero-mobile.png'

const windowSize = ref(window.innerWidth)

const hero = computed(() => {
    if (windowSize.value < 400) {
        return HeroMobile
    } else {
        return HeroDesktop
    }
})

onMounted(() => {
    window.addEventListener('resize', () => {
        windowSize.value = window.innerWidth
    })
})

onUnmounted(() => {
    window.removeEventListener('resize')
})

</script>

<template>
    <main class="wrapper">
        <div class="content">
            <h1>Make remote work</h1>
            <p>Get your team in sync, no matter your location. Streamline processes, create team rituals, and watch productivity soar.</p>

            <button class="learn-more">Learn More</button>
        </div>

        <img :src="hero" alt="" class="hero">


        <div class="clients">
            <img class="client" src="../assets/images/client-databiz.svg" alt="">
            <img class="client" src="../assets/images/client-audiophile.svg" alt="">
            <img class="client" src="../assets/images/client-meet.svg" alt="">
            <img class="client" src="../assets/images/client-maker.svg" alt="">
        </div>
    </main>
</template>

<style scoped>
.wrapper{
    padding: 2em 0;

    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr auto;
    column-gap: 3.2em;
}

.hero {
    max-height: 70vh;
    max-width: 100%;
    grid-row: 1/3;
}
.content {
    grid-column: 1;
    grid-row: 1;

    padding: 10%;
}

.content h1 {
    color: var(--almost-black);
    font-size: 3em;
}

.learn-more {
    font-family: inherit;
    color: var(--almost-white);

    background-color: var(--almost-black);
    border: none;
    border-radius: 10px;

    padding: .9em 1.4em;
    margin-top: 3em;
}

.clients {
    padding: 0 10%;
}
.client {
    margin: 0 1em;
}

@media screen and (width < 400px) {
    .wrapper {
        grid-template-columns: 1fr;
        grid-template-rows: auto auto auto;
    }

    .hero {
        grid-row: 1;
    }

    .content {
        grid-row: 2;
    }

    .clients {
        grid-row: 3;
    }
}
</style>