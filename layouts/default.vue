<script setup>
import { Icon } from '#components'
</script>

<template>
  <div id="root">
    <header>
      <nav>
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="about">About</NuxtLink>
        <NuxtLink to="portfolio">Portfolio</NuxtLink>
        <NuxtLink to="contact">Contact</NuxtLink>
        <div class="social-icons">
          <NuxtLink to=""><Icon size="32" name="uil:github"></Icon></NuxtLink>
          <NuxtLink to=""><Icon size="32" name="logos:codepen-icon"></Icon></NuxtLink>
        </div>
        <p class="p-email">d4ndres@gmail.com</p>
      </nav>
    </header>
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
  padding: 0 2rem;
}
header{
  grid-column: span 1;
  display: flex;
  justify-content: center;
}
nav{
  display: flex;
  flex-direction: column;
  gap: 2rem;
  align-items: center;
  min-height: 100vh;
  position: fixed;
  top: 0;
}
.social-icons{
  display: flex;
  gap: 1rem;
}

.router-link-active{
  color: var(--primary)
}

.p-email{
  font-size: 1rem;
}
</style>
