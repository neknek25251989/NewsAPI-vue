<template>
    <div id="app">
        <Menu></Menu>
        <news-list v-bind:info="info"></news-list>


    </div>
</template>

<script>
    import Menu from './menu.vue';
    import NewsList from './newsList.vue';
    export default {
        name: 'app',
        data() {
            return {
                info: [],
            }
        },
        components: {
            Menu,
            NewsList
        },
        mounted() {
            console.clear();
            const url = 'https://newsapi.org/v2/top-headlines';

            this.axios.get(url, {
                    params: {
                        country: 'tw',
                        apiKey: '357af6ad6bcb4fdf8945b9c5f1b8d3d1',
                        category: 'business'
                    }
                })
                .then(response => this.info = response.data.articles)

                .catch(function(error) {
                    console.log(error);
                });
        }
    }
</script>

<style lang="scss">

</style>