<script setup>
import { Icon } from '#components'
</script>

<template>
  <div id="root">
    <nav>
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="about">About</NuxtLink>
      <NuxtLink to="portfolio">Portfolio</NuxtLink>
      <NuxtLink to="contact">Contact</NuxtLink>
      <div class="social-icons">
        <NuxtLink to=""><Icon size="32" name="uil:github"></Icon></NuxtLink>
        <NuxtLink to=""><Icon size="32" name="logos:codepen-icon"></Icon></NuxtLink>
      </div>
    </nav>
    <main>
      <slot />
    </main>
  </div>
</template>

<style scoped>
#root{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}
main{
  grid-column: span 3;
}
nav{
  display: flex;
  flex-direction: column;
  gap: 2rem;
  align-items: center;
}
.social-icons{
  display: flex;
  gap: 1rem;
}


</style>
