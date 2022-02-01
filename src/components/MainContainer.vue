<template>
    <main>
        <div class="container d-flex flex-wrap justify-content-between">
            <disc-box v-for="(disco, index) in dischiList" 
                :key="index"
                :disco="disco"/>
        </div>
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
