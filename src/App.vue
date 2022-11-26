<template>
    <div class="cursor" :style="{transform: `translate3d(${cursor.x}px, ${cursor.y}px, 0)`}">
        click
    </div>
    <!-- <div class="cursor" :style="{left: `${cursor.x}px`, top:`${cursor.y}px`}">
        click
    </div> -->
    <Header :pageScroll="pageScroll" />
    <Section1 :pageScroll="pageScroll" />
    <Section2 :pageScroll="pageScroll" />
    <!-- <Section /> -->
    <!-- <Section /> -->
    <!-- <Footer /> -->
</template>

<script>
import Header from './components/Header.vue';
import Section1 from './components/Section1.vue';
import Section2 from './components/Section2.vue';


// import Section from './components/Section.vue';
// import Footer from './components/Footer.vue';

export default {
    name: 'App',
    data() {
        return {
            pageScroll: false,
            cursor: {
                x: 0,
                y: 0
            }
        }
    },
    components: {
        Header,
        Section1,
        Section2,
        // Section,
        // Footer,
    },
    mounted() {
        document.body.onscroll = () => {
            let scrollTop = (window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop)
            this.pageScroll = scrollTop;
        }

        window.addEventListener("mousemove", (e) => {
                this.cursor.x = e.pageX;
                this.cursor.y = e.pageY;
            },
        ) 
    }
}
</script>

<style lang="scss">
.body {
    scroll-behavior: smooth;
    overscroll-behavior: none;
}

::-webkit-scrollbar {
    display: none;
}

.cursor {
    width: 100px;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    top: 0;
    left: 0;
    overflow: hidden;
    background: rgba(0,0,0,.15);
    -webkit-backdrop-filter: blur(20px);
    backdrop-filter: blur(20px);
    border-radius: 100%;
    z-index: 9995;
    transition: 0.1s;
    transition-delay: 0s;
    pointer-events: none;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: white;
    height: 120vh;
    scrollbar-width: 0;
}
</style>
