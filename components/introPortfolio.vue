<script setup>
const portfolioData = [
    { state: true, title: 'IP address tracker ', description: 'This web is a project that shows you the geographical location, the time in UTC and the ISP of the searched IP address or by default your IP address.',imglg: '/portfolio/ip-address-tracker.png', imgsm: '/portfolio/ip-address-tracker-375.png', link: 'https://ip-address-tracker-ecosystem-vue.vercel.app', technologies: ['Vue', 'IP Geolocation API', 'leafletjs API'] },
    { state: true, title: 'Space tourism coming soon',  description: 'A static and informative website about the most ambitious destinations of the century. He knows the distance that lies ahead, the time it would take us to arrive, crew members that you could only perhaps run into in space tourism.', imglg: '/portfolio/space-tourism-coming-soon.png', imgsm: '/portfolio/space-tourism-coming-soon-768.png', link: 'https://space-tourism-coming-soon.vercel.app', technologies: ['Vue', 'Vuex', 'VueRouter'] },
    { state: true, title: 'Time tracking dashboard', description: 'A tool that allows you to record and have a history of how much time you have dedicated to your fundamental activities.', imglg: '/portfolio/time-tracking-dashboard.png', imgsm: '/portfolio/Time-tracking-dashboard-375.png', link: 'https://03-time-tracking-dashboard.vercel.app', technologies: ['Vue'] }
]
const experimentsData = [
    {title: 'Profile card component', url: 'https://profile-card-component-main-pi-fawn.vercel.app/'},
    {title: 'NFT preview card component', url: 'https://nft-preview-card-component-black.vercel.app/'},
    {title: 'Stats preview card component', url: 'https://stats-preview-card-component-mobile-first.vercel.app/'},
    {title: 'Notification page component', url: 'https://01-notifications-page.vercel.app/'},
    {title: 'Text negative bg', url: 'https://codepen.io/d4ndres/full/bGNPBWW'},
    {title: 'Dandelion interactive', url: 'https://codepen.io/d4ndres/full/ExYwXNV'},
    {title: 'Pong interactive', url: 'https://codepen.io/d4ndres/full/YdWXNQ'},
    {title: 'Particles interactive', url: 'https://codepen.io/d4ndres/full/BvjQea'},
    {title: 'Fire challenge', url: 'https://codepen.io/d4ndres/full/BvQgXE'},
]
let iframeURL = ref('https://codepen.io/d4ndres/full/BvQgXE')

</script>
<template>
<section>
    <h2>My Portfolio</h2>
    <article>
        <h3>Productos</h3>
        <p>
            I love to code. I strongly believe that everything that 
            can be imagined in code will come true. 
            <br>
            Here some of my projects.
        </p>
        <div v-for="project in portfolioData" :key="project.link">
            <project  :project="project"/>
        </div>
    </article>
    <article>
        <h3>Experiments</h3>
        <p>
            I have spent a lot of time on different web experiments. 
            Mainly to have fun and learn new technologies. 
            This habit keeps me informed of the latest technologies 
            and prepares me to take on new challenges.
        </p>
        <div class="experiments-show">
            <ul>
                <li v-for="experiment in experimentsData" :key="experiment">
                    <a 
                    :class="{ 'active' : iframeURL == experiment.url}" 
                    @click.prevent="iframeURL = experiment.url">
                        {{ experiment.title }}
                    </a>
                </li>
            </ul>
            <div class="wrap">
                <iframe :src="iframeURL" class="frame"></iframe>
            </div>
        </div>
    </article>

</section>
</template>

<style scoped>
    section {
        padding-bottom: 5rem;
    }

    article{
        margin: 1rem 0;
    }
    h3 {
        margin-bottom: .25rem;
    }


    .experiments-show{
        margin: 2rem 0;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        padding: 0 1rem;
        gap: 1rem;  
    }
    .wrap {
        width: 450px;
        height: calc( 450px * 9/16);
        padding: 0;
        overflow: hidden;
        background-image: url('/logocat.png');
        background-position: center center;
        background-size: 40%;
        background-repeat: no-repeat;
        filter: blur(100%);
    }
    .frame {
        width: 1024px;
        height: 580px;
        border: 0;
        -ms-transform: scale(calc( 450/1024));
        -moz-transform: scale(calc( 450/1024));
        -o-transform: scale(calc( 450/1024));
        -webkit-transform: scale(calc( 450/1024));
        transform: scale(calc( 450/1024));

        -ms-transform-origin: 0 0;
        -moz-transform-origin: 0 0;
        -o-transform-origin: 0 0;
        -webkit-transform-origin: 0 0;
        transform-origin: 0 0;
    }

    @media screen and ( max-width: 768px ){
        .frame{
            -ms-transform: scale(calc( 310/1024));
            -moz-transform: scale(calc( 310/1024));
            -o-transform: scale(calc( 310/1024));
            -webkit-transform: scale(calc( 310/1024));
            transform: scale(calc( 310/1024));           
        }
        section {
            padding-bottom: 0rem;
        }
    }
</style>