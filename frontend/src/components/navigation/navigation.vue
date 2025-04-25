<template>
    <nav class="nav">
        <section class="nav__wrapper">
            <figure class="nav__figure">
                <img src="../../assets/logo.png" alt="" class="nav__img">
            </figure>
            <button class="nav__selection">
                For you
                <SvgIcon :name="'chevron-short'" />
            </button>
            <ul class="nav__dropdown">
                <li class="nav__dropdown--items">
                    For you
                </li>
                <li class="nav__dropdown--items">
                    Friends
                </li>
            </ul>
        </section>
        <section class="nav__wrapper">
            <button class="nav__button">
                <SvgIcon :name="'find-people'" />
            </button>
            <button class="nav__button">
                <SvgIcon :name="'bell'" />
            </button>
            <button class="nav__button">
                <SvgIcon :name="'chat'" />
            </button>
        </section>
    </nav>
</template>

<script>

import SvgIcon from '../general/SvgIcon.vue';

export default {
    name: "NavigationComponent",
    components: {
        SvgIcon
    }
}

</script>