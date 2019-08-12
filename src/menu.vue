<template>
    <div>
        <b-nav class="category"
            small
            fill>
            <b-nav-item class="category__item"
                v-for="(category, index) in categories"
                :key="index"
                @click="changeCategory">{{category.toUpperCase()}}</b-nav-item>
        </b-nav>
    </div>
</template>

<script>
    import { BNav, BNavItem } from 'bootstrap-vue'
    export default {
        components: {
            BNav,
            BNavItem
        },
        data() {
            return {
                categories: [
                    'all',
                    'business',
                    'entertainment',
                    'general',
                    'health',
                    'science',
                    'sports',
                    'technology'
                ]
            }
        },
        methods: {
            changeCategory: function(e) {
                this.$emit('selectCategory', e);
            }
        },
    }
</script>

<style lang="scss"
    scoped>
    .category {
        &__item {
            a {
                color: #787878;

                &:hover {
                    color: #454545;
                }
            }
        }
    }
</style>