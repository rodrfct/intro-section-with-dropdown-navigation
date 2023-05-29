# Frontend Mentor - Intro section with dropdown navigation solution

This is a solution to the [Intro section with dropdown navigation challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/intro-section-with-dropdown-navigation-ryaPetHE5). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)


## Overview

### The challenge

Users should be able to:

Users should be able to:

- [x] View the relevant dropdown menus on desktop and mobile when interacting with the navigation links
- [x] View the optimal layout for the content depending on their device's screen size
- [x] See hover states for all interactive elements on the page


### Links

- Solution URL: [My Solution]()
- Live Site URL: [My Live Site](https://rodrfct.github.io/intro-section-with-dropdown-navigation/)

## My process

### Built with

- CSS Grid
- [Vue](https://vuejs.org/) (Complete overkill I know)



### What I learned

Overall I got better with Grid and learned to make the dropdown menus. At first I tried using `display: none` but it kills the posibility to use transitions.

Additionally I learned to use reative images in Vue.

```javascript
import { computed, onMounted, onUnmounted, ref } from 'vue';
import HeroDesktop from '../assets/images/image-hero-desktop.png'
import HeroMobile from '../assets/images/image-hero-mobile.png'

const windowSize = ref(window.innerWidth)

const hero = computed(() => {
    if (windowSize.value < 420) {
        return HeroMobile
    } else {
        return HeroDesktop
    }
})

const getWindowSize = () => {
    windowSize.value = window.innerWidth
}

onMounted(() => {
    window.addEventListener('resize', getWindowSize)
})

onUnmounted(() => {
    window.removeEventListener('resize', getWindowSize)
})
```