<template>
    <div id="app">
        <Menu></Menu>
        <news-list :news="news"></news-list>
    </div>
</template>

<script>
    import Menu from './menu.vue'
    import NewsList from './newsList.vue'
    export default {
        name: 'app',
        data() {
            return {
                news: [],
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
                        country: 'us',
                        apiKey: '357af6ad6bcb4fdf8945b9c5f1b8d3d1',
                        category: 'science'
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