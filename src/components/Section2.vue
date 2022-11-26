<template>
    <section ref="section2" class="section2">
      <h1 class="section2__title" :style="{'width': `calc(85% - ${offset}px)`}">
        <span :style="{'transform': `translate3d(${(offset / 3 < 67) ? offset / 3 : 67}px, 0, 0)`}">Play</span>
        <div class="section2__img-container">
            <img class="section2__img" 
              :style="{'width': `calc(200px + ${offset * 2}px)`}"
              src="https://fikiwiki.com/uploads/posts/2022-02/1644855593_25-fikiwiki-com-p-kartinki-khd-kachestva-26.jpg" />
        </div>
        <span :style="{'transform': `translate3d(-${(offset / 3 < 67) ? offset / 3 : 67}px, 0, 0)`}">Reel</span>
      </h1>
    </section>
</template>

<script>
export default {
    name: 'Section2',
    // components: {},
    props: {
        pageScroll: {
            type: Number
        }
    },
    data: () => ({
        offset: 0
    }),
    mounted() {
        window.addEventListener("scroll", () => {
            console.log(this.pageScroll - this.$refs.section2.offsetTop)
            if (this.$refs.section2.offsetTop < this.pageScroll) {
                this.offset = this.pageScroll - this.$refs.section2.offsetTop
            }
        });
    }
    // methods: {},
};
</script>

<style lang="scss" scoped>
.section2 {
    height: 150vh;
    min-height: 1000px;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    width: 100%;
    max-width: 1024px;
    padding: 32px;
    position: relative;
    background: black;
    background-size: cover;
    background-repeat: no-repeat;
}

.section2__title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 100px;
    width: 85%;
    min-width: 555px;
    margin: 200px auto;
    color: white;
    font-weight: 400;
}

.section2__img-container {
    width: 1px;
    max-width: 1px;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: visible;
}

.section2__img {
    width: 200px;
    justify-self: center;
}
</style>
