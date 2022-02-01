<template>
    <div>
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
        </div>
        <div class="d-flex justify-content-center">
            <span>Filtro per artista:</span>
            <select v-model="selectedArtist">
                <option disabled value="">Scegli un genere</option>
                <option value="All">All</option>
                <option value="Bon Jovi">Bon Jovi</option>
                <option value="Queen">Queen</option>
                <option value="Sting">Sting</option>
                <option value="Steve Gadd Band">Steve Gadd Band</option>
                <option value="Iron Maiden">Iron Maiden</option>
                <option value="Eric Clapton">Eric Clapton</option>
                <option value="Deep Purple">Deep Purple</option>
                <option value="Metallica">Metallica</option>
                <option value="Dave Weckl">Dave Weckl</option>
                <option value="Michael Jacjson">Michael Jacjson</option>
            </select>
            <span @click="$emit('filtroArtist', selectedArtist)">Search</span>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selectedValue: '',
            selectedArtist: ''
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