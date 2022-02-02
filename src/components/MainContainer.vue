<template>
    <main>
        <div class="ms_search d-flex justify-content-center">
            <span>Cerca:</span>
            <input type="text" v-model="searchInput" placeholder="Cerca">
        </div>
        <div class="container d-flex flex-wrap justify-content-start">
            <disc-box v-for="(disco, index) in dischiList" 
                :key="index"
                :disco="disco"
                :search="searchInput"/>
        </div>
    </main>
</template>

<script>
import DiscBox from '../components/DiscBox.vue'

export default {
    data() {
        return {
            searchInput: '',
        }
    },
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
        padding: 50px 0 100px;

        .ms_search {
            color: #fff;
            font-size: 24px;
            margin-bottom: 30px;

            span {
                margin-right: 20px;
            }
        }

        div {
            margin: 0 auto;
        }
    }
</style>
