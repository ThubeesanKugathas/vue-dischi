<template>
    <main>
        <disc-box v-for="(disco, index) in dischiList" 
            :key="index"
            :disco="disco"/>
    </main>
</template>

<script>
import DiscBox from '../components/DiscBox.vue'

export default {
    components: {
        DiscBox,
    },
    props: {
        dischiList: Array,
    }
}
</script>

<style lang="scss" scoped>
    main {
        background-color: #1e2d3b;
        padding: 100px 0;
    }
</style>

// "success": true,
    "response": [
        {
            "poster": "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg",
            "title": "New Jersey",
            "author": "Bon Jovi",
            "genre": "Rock",
            "year": "1988"
        },
// 