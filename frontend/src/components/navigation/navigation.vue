<template>
    <nav class="nav">
        <section class="nav__wrapper">
            <figure class="nav__figure">
                <img src="../../assets/logo.png" alt="" class="nav__img">
            </figure>
            <button class="nav__selection" @click="toggleDropdown($event)">
                For you <SvgIcon :name="'chevron-short'" />
            </button>
            <ul ref="dropdown" class="nav__dropdown" :class="dropdownIsActive ? `nav__dropdown--active` : ``">
                <li class="nav__dropdown--items">
                    For you
                </li>
                <li class="nav__dropdown--items">
                    Friends
                </li>
            </ul>
        </section>
        <section class="nav__ButtonWrapper">
            <button class="nav__button">
                <SvgIcon :name="'heart'" />
            </button>
            <button class="nav__button">
                <SvgIcon :name="'find-people'" />
            </button>
            <button class="nav__button">
                <SvgIcon :name="'bell'" />
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
    },
    data() {
        return {
            dropdownIsActive: false
        };
    },
    methods: {
        toggleDropdown(event) {
            this.dropdownIsActive = !this.dropdownIsActive;
            event.stopPropagation(); 
        },
        handleClickOutside(event) {
             if (this.dropdownIsActive && this.$refs.dropdown && !this.$refs.dropdown.contains(event.target) && event.target !== this.$el.querySelector('.nav__selection')) {
                this.dropdownIsActive = false;
            }
        }
    },
    mounted() {
        document.addEventListener('click', this.handleClickOutside);
    },
    beforeUnmount() {
        document.removeEventListener('click', this.handleClickOutside);
    }
};
</script>