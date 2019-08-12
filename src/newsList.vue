<template>
    <div>
        <b-row>
            <b-col md="12"
                v-for="(item, index) in news"
                :key="index">
                <a :href="item.url"
                    target="_blank">
                    <b-card overlay
                        class="news"
                        :img-src="item.urlToImage || 'https://dummyimage.com/600x400/000000/ffffff&text=no+photo'"
                        :img-alt="item.title"
                        text-variant="white">
                        <b-card-body body-class="news__context">
                            <b-card-title title-tag="div"
                                class="news__title">{{item.title.split(' - ').splice(0, 1).join()}}</b-card-title>
                            <b-card-sub-title sub-title-tag="div"
                                class="news__source">{{item.source.name}}</b-card-sub-title>
                            <b-card-text class="news__description">{{item.description}}</b-card-text>
                        </b-card-body>
                    </b-card>
                </a>
            </b-col>
        </b-row>
    </div>
</template>

<script>
    import {
        BCard,
        BCardBody,
        BCardTitle,
        BCardSubTitle,
        BCardText,
        BCol,
        BRow
    } from 'bootstrap-vue'
    export default {
        props: ['news'],
        components: {
            BCard,
            BCardBody,
            BCardTitle,
            BCardSubTitle,
            BCardText,
            BCol,
            BRow
        },
    }
</script>

<style lang="scss"
    scoped>
    .news {
        margin: 24px 0;
        position: relative;
        overflow: hidden;

        img {
            transition: 0.2s;
        }

        &:hover {
            img {
                transform: scale(1.1);
                transition: 0.5s
            }
        }

        &__context {
            position: absolute;
            width: 100%;
            left: 0;
            bottom: 0;
            background-image: linear-gradient(180deg, rgba(0, 0, 0, 0), rgba(0, 0, 0, 1))
        }

        &__title {
            font-size: 24px;
            font-weight: bold;
        }

        &__source {
            font-size: 20px;
            font-weight: bold;
        }

        @media screen and (max-width: 768px) {
            &__title {
                font-size: 18px;
            }

            &__source {
                font-size: 14px;
            }

            &__description {
                display: none;
            }
        }
    }
</style>