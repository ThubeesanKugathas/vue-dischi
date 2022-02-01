<template>
    <div class="d-flex justify-content-center">
        <span>Filtro per genere:</span>
        <select v-model="selectedValue">
            <option disabled value="">Scegli un genere</option>
            <option value="All">All</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="Pop">Pop</option>
            <option value="Rock">Rock</option>
        </select>
        <span @click="$emit('filtro', selectedValue)">Search</span>
        <span>Reset</span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selectedValue: ''
        }
    }
}
</script>

<style lang="scss" scoped>
    div {
        background-color: #1e2d3b;
        text-align: center;
        color: #fff;
        padding-top: 50px;
        font-size: 25px;
        
        select {
            margin: 0 20px;
        }

        span {
            margin: 0 20px;
        }
    }
</style>