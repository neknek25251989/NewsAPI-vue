<template>
    <div id="app">
        <b-container>
            <Header></Header>
            <Menu v-on:selectCategory="changeCategory"></Menu>
            <news-list v-bind:news="news"></news-list>
        </b-container>
    </div>
</template>

<script>
    import Menu from './menu.vue'
    import NewsList from './newsList.vue'
    import Header from './header.vue'
    import { BContainer } from 'bootstrap-vue'
    export default {
        name: 'app',
        data() {
            return {
                news: [],
            }
        },
        components: {
            Header,
            Menu,
            NewsList,
            BContainer
        },
        mounted() {
            this.getNews();
        },
        methods: {
            changeCategory: function(e) {
                const newsType = (e.target.text.toLowerCase() == 'all') ? '' : (e.target.text.toLowerCase())
                this.getNews(newsType);
            },
            getNews: function(type) {
                const url = 'https://newsapi.org/v2/top-headlines';
                this.axios.get(url, {
                        params: {
                            country: 'us',
                            category: type,
                            apiKey: '357af6ad6bcb4fdf8945b9c5f1b8d3d1',
                        }
                    })
                    .then(response => this.news = response.data.articles)
                    .catch(function(error) {
                        console.log(error);
                    });
            }
        },
    }
</script>

<style lang="scss">
</style>