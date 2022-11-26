<template>
    <header>
        <nav class="nav" :style="{opacity: (pageScroll ? 0 : 1)}">
            <p class="logo">
                Logo
            </p>
            <ul class="nav__menu">
                <li class="nav__menu-item menu__item">
                    Work
                    <span class="menu-item__underline"></span>
                </li>
                <li class="nav__menu-item menu__item">
                    Studio
                    <span class="menu-item__underline"></span>
                </li>
                <li class="nav__menu-item menu__item">
                    News
                    <span class="menu-item__underline"></span>
                </li>
                <li class="nav__menu-item menu__item">
                    Contact
                    <span class="menu-item__underline"></span>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
  name: 'Header',
  // components: {},
  props: {
        pageScroll: {
            type: Number
        }
  },
  // data: () => ({}),
  // methods: {},
  
};
</script>

<style lang="scss" scoped>
.nav {
    position: fixed;
    z-index: 9990;
    height: 100px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    max-width: 1024px;
    padding: 32px;
    transition: opacity 0.15s;
}

.logo {
    color: white;
}

.nav__menu {
    display: flex;
    padding: 0;
    margin: 0;
    gap: 40px;
    list-style: none;
    color: white;
}

.nav__menu-item {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-end;
    & .menu-item__underline {
        display: block;
        width: 0%;
        border-bottom: 2px solid white;
        transition: 0.25s cubic-bezier(.71,.27,1,.51);
    }
    &:hover {
        cursor: pointer;
        align-items: flex-start;
        & .menu-item__underline {
            transition: 0.5s ease-out;
            transition-delay: 0.2s;
            width: 100%;
        }
    }
}
</style>
