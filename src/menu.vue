<template>
    <div>
        <ul>
            <li v-for="(category, index) in categories" :key="index">
                <router-link>{{category}}</router-link>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                categories: [
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
    }
</script>

<style lang="scss" scoped>

</style>