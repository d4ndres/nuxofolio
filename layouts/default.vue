<script setup>
import { Icon } from '#components'
</script>

<template>
  <div id="root">
    
    <CanvasBg/>
    
    <header>
      <nav>
        <NuxtLink to="/" class="logo deactivate"><img src="@/public/logocat.png" alt="Logo"></NuxtLink>
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/about">About</NuxtLink>
        <NuxtLink to="/portfolio">Portfolio</NuxtLink>
        <NuxtLink to="/contact">Contact</NuxtLink>
        <!-- <div class="social-icons">
          <NuxtLink to=""><Icon size="32" name="uil:github"></Icon></NuxtLink>
          <NuxtLink to=""><Icon size="32" name="logos:codepen-icon"></Icon></NuxtLink>
        </div> -->
      </nav>
    </header>
    <main>
      <slot />
    </main>
  </div>
</template>

<style scoped>
.canvas {
  position: absolute;
}

#root{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}
main{
  grid-column: span 3;
  margin: 0 auto 0 0 ;
  width: 90%;
}
header{
  grid-column: span 1;
  display: flex;
  justify-content: center;
}
nav{
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
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



@media screen and ( max-width: 768px){
  #root{
    grid-template-columns: 1fr;
    overflow: hidden;
  }
  main{
    margin: 0 auto;
  }
  header{
    transform: translateX(100%);
  }
}
a img {
  width: min(100px, 10vw);
}



</style>
