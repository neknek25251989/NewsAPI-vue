<template>
    <div>
        <ul class="newsList">
            <li v-for="(item, index) in news" :key="index" class="news">
                <div class="news__img" v-bind:style="{ 'background-image': 'url(' + item.urlToImage + ')' }"></div>
                <div class="news__title">
                    {{item.title}}
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        props: ['news']
    }
</script>

<style lang="scss" scoped>
    .news {
        width: 200px;
        height: 300px;
        list-style-type: none;

        &__img {
            width: 200px;
            height: 150px;
            background-repeat: no-repeat;
            background-size: contain;
        }

        &__title {
            height: 150px;
        }
    }
</style>