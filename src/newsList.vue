<template>
    <div>
        <ul>
            <li v-for="(item, index) in news" :key="index">{{item.title}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        props: ['news']
    }
</script>