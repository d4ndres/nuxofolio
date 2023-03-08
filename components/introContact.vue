<script lang="ts" setup></script>

<template>
  <section>
    <h2>Contact me</h2>
    <article class="contact-message">
      <p>
        If you are interested to hire me
        <br>
        I am always open to new opportunities and interesting projects! 
        <br>
        Feel free to contact me if you have any other requests 
        or questions regarding web development.
      </p>
      <div class="send-email">
        <NuxtLink class="btn" to="mailto:d4ndres@gmail.com">
            <Icon size="32" name="material-symbols:mail-outline"></Icon>
            <p>Send email</p>
        </NuxtLink>
      </div>
    </article>
    
    <article class="all-links">
      <h3>Links</h3>
      <ul class="links">
        <li>
          <NuxtLink class="btn" target="_blank" to="https://codepen.io/d4ndres">
            <Icon size="32" name="logos:codepen-icon"></Icon><p>Codepen</p>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink class="btn github" target="_blank" to="https://github.com/d4ndres">
            <Icon size="32" name="logos:github-icon"></Icon><p>GitHub</p>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink class="btn" target="_blank" to="https://www.linkedin.com/in/diego-andr%C3%A9s-rojas-gonz%C3%A1lez-68715915b/">
            <Icon size="32" name="logos:linkedin-icon"></Icon><p>LinkedIn</p>
          </NuxtLink>
        </li>
      </ul>
    </article>
  </section>
</template>

<style scoped>

section{
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  text-align: justify;
}
.send-email {
  margin: 1rem 0;
}

.contact-message{
  margin: 1rem 0;
}


.intro {
  min-height: 100vh;

}

.links {
  display: flex;
  gap: 2rem;
}

a p{
  display: inline-block;
  margin-left: 1rem;
}

h3 {
  margin-bottom: 1rem;
}

.all-links {
  margin: 1rem 0;
}
@media screen and ( max-width: 768px ){
  .links{
    flex-direction: column;
  }
  .btn{
    width: 80vw;
  }
}
</style>
