<script setup>
const technologies = [
  {text: 'Vue', icon: 'vue'},
  {text: 'Vue Router', icon: 'vue'},
  {text: 'Vuex', icon: 'vue'},
  {text: 'Nuxt', icon: 'nuxt-icon'},
  {text: 'FastAPI', icon: 'python'},
  {text: 'MongoDB', icon: 'mongodb-icon'},
  {text: 'Git', icon: 'git-icon'},
  {text: 'Figma', icon: 'figma'},
  {text: 'VSCode', icon: 'visual-studio-code'},

]

</script>

<template>
  <section class="introAbout">
    <article class="hook">
      <h2>About me</h2>
      <p>
        I use my passion and skills to build products and experiences.

        I've been currently working for Helexium and freelancing on small projects in my free time. 
        I have experience with various programming languages and specifically web technologies.

        My motivation for developing this website is to share my learnings with the rest of the world.
        Along with developing software, I enjoy traveling, going to live music events, discovering something new, and hanging out with my friends.
      </p>
    </article>
    <article class="some-technologies">
        <h3>Here are some tools and technologies I like to work with:</h3>
        <ul>
          <CardTechnologies :technologies="technologies" title="Web development" />
        </ul>
        <div class="inline-block">
          <NuxtLink>
              More about me
          </NuxtLink>
        </div>
      </article>
  </section>
</template>

<style scoped>
.introAbout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
h2 {
  margin-bottom: 1.5rem;
}

.hook {
  text-align: justify;
  
}
.inline-block{
  display: inline-block;
}

</style>
