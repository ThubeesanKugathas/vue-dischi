<template>
    <div class="d-flex justify-content-center">
        <div class="d-flex justify-content-center">
            <span>Filtra per:</span>
            <select v-model="selectedType" @change="filterReset">
                <option disabled value="">Tipo</option>
                <option value="author">Autore</option>
                <option value="genre">Genere</option>
            </select>
        </div>
        <!-- FILTER PER GENERE -->
        <div class="d-flex justify-content-center" v-if="this.selectedType === 'genre'">
            <span>Genere:</span>
            <select v-model="selectedValue" @change="$emit('filtro', selectedValue)">
                <option disabled value="">Scegli un genere</option>
                <option value="All">All</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
                <option value="Pop">Pop</option>
                <option value="Rock">Rock</option>
            </select>
        </div>

        <!-- FILTRO PER ARTISTA -->
        <div class="d-flex justify-content-center" v-if="this.selectedType === 'author'">
            <span>Artista:</span>
            <select v-model="selectedArtist" @change="$emit('filtroArtist', selectedArtist)">
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
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selectedValue: '',
            selectedArtist: '',
            selectedType: '',
        }
    },
    methods: {
      filterReset() {
          if (this.selectedType === 'genre') {
              this.$emit('filtro', 'All');

              this.selectedValue = '';
          } else {
              this.$emit('filtroArtist', 'All');

              this.selectedArtist = '';
          }
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