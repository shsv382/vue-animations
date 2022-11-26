<template>
    <section ref="section" class="section1" :style="{backgroundPositionY: `${pageScroll / 2}px`}">
      <h1 class="section1__title">Digital design experience</h1>
    </section>
</template>

<script>
export default {
    name: 'Section1',
    // components: {},
    props: {
        pageScroll: {
            type: Number
        }
    },
    data: () => ({
    }),
    // methods: {},
};
</script>

<style lang="scss" scoped>
.section1 {
    height: 150vh;
    min-height: 800px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    max-width: 1024px;
    padding: 32px;
    position: relative;
    background: url("https://i.pinimg.com/originals/f5/91/3f/f5913ff85bc9f2057d925ef7c74e56aa.jpg");
    background-size: cover;
    background-repeat: no-repeat;
}

.section1__title {
    font-size: 140px;
    width: 80%;
    color: white;
    font-weight: 400;
}
</style>
