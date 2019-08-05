<template>
    <div>
        <ul>
            <li v-for="(item, index) in info" :key="index">{{item.title}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        props: ['info']
    }
</script>