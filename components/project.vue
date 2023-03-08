<script setup>
import { Icon } from '#components'  
const { project } = defineProps(['project'])
let isDesktop = useState(`isDesktop${project.title}`, () => true)
</script>


<template>
  <div class="project">
    <div class="project__img" :class="{ 'active': !isDesktop}">
      <Icon class="framework-icon" v-if="project.technologies.includes('Vue')" size="1.5rem" :name="`logos:vue`"></Icon>
      <Icon class="framework-icon" v-if="project.technologies.includes('Nuxt')" size="1.5rem" :name="`logos:nuxt`"></Icon>
      <img v-show="isDesktop" :src="project.imglg" :alt="project.imglg">
      <img v-show="!isDesktop"  :src="project.imgsm" :alt="project.imgsm">
    </div>
    
    <div class="project__about">
      <h4>{{ project.title }}</h4>
      <p>
        {{ project.description }}
      </p>
      <ul>
        <li v-for="technology in project.technologies" :key="technology">
          {{ technology }}
        </li>
      </ul>
      <div >
        <NuxtLink target="_blank" :to="project.link">
          <Icon size="1.5rem" :name="`material-symbols:open-in-new`"></Icon>
        </NuxtLink>
      </div>
      <div class="isDesktop">
        <p :class="{ 'active': isDesktop }" @click="isDesktop = false" >Desktop</p>
        <toggle :title="project.title"/>
        <p :class="{ 'active': !isDesktop }" @click="isDesktop = true">Movile</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.project {
  padding: 1rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 280px;
  gap: 1rem;
}
.project__about{
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.project__about p{
 font-size: 1rem;
}

.project__img{
  position: relative;
}
.framework-icon {
  position: absolute;
  left: 10px;
  top: 10px;
  opacity: .5;
}
img {
  width: 100%;
  height: 100%;
}
.project__img.active {
  display: flex;
  justify-content: center;
  align-items: center;
}

.project__img.active img {
  width: auto;
}

ul {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}
.isDesktop{
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  height: 50px;
  width: 100%;
}
.isDesktop p{
  width: 58px;
  cursor: pointer;
  transition: .4s;
}
.isDesktop p:first-child{
  text-align: right;
}
.isDesktop p:last-child{
  text-align: left;
}

.isDesktop .active {
  font-weight: 700;
}
@media screen and ( max-width: 768px ){
  .project{
    margin: 5rem 0;
    grid-template-columns: 1fr;
    grid-template-rows: 200px;
    
  }
}
</style>
