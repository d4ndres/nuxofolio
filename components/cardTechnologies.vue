<script setup>
    import { Icon } from '#components'  
    const { technologies, title } = defineProps(['technologies', 'title'])
</script>
<template>
    <div class="technologies">
        <h3>{{ title }}</h3>
        <ul>
            <li class="technology" v-for="technology in technologies" :key="technology.text">
                <p> <Icon size="1.5rem" :name="`logos:${technology.icon}`"></Icon> {{ technology.text }}</p>
            </li>
        </ul>
    </div>
</template>
<style scoped>

.technologies {
    border: solid 1px var(--secondary);
    padding: 1rem;
    box-shadow: .4rem .4rem 0 1px rgba(0,0,0,.4);
    width: min(375px, 80%);
    margin: 2rem auto;
    transition: .8s;
}
.technologies:hover {
    border: solid 1px #000;
    box-shadow: 0rem 0rem 0 0px rgba(0,0,0,.8);
}

h3 {
    margin: 1rem 0;
}
ul {
    display: grid;
    gap: .5rem;
    grid-template-columns: repeat( auto-fill, minmax(150px, 1fr));
}
p {
    font-size: 1rem;
}

</style>