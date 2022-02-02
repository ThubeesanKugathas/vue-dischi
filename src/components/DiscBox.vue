<template>
    <div class="ms_card-container" 
        v-if="disco.title.toLowerCase().includes(search) || 
        disco.author.toLowerCase().includes(search) ||
        disco.year.includes(search)">
        <img :src="disco.poster" :alt="disco.title">
        <h1>
            {{disco.title.toUpperCase()}}
        </h1>
        <div class="ms_author">
            <p>{{disco.author}}</p>
            <p>{{disco.year}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        disco: Object,
        search: String,
    }
}
</script>

<style lang="scss" scoped>
    .ms_card-container {
        background-color: #2e3a46;
        padding: 20px;
        width: calc((100% - 100px) / 5);
        text-align: center;
        margin: 10px;

        img {
            width: 100%;
        }

        h1 {
            color: #fff;
            font-size: 24px;
            margin: 20px;
            font-weight: bold;
        }

        .ms_author {
            color: #888;

            p {
                margin: 0;
                font-size: 20px;
            }
        }
    }
</style>

