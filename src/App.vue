<template>
  <div id="app">
    <header-box />
    <filter-box @filtro="filterGenre" @filtroArtist="filterArtist" @filtroType="filterType"/>
    <loader-div v-if="!flagLoader" />
    <main-container v-else :dischiList="filteredDischi"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import FilterBox from './components/FilterBox.vue'
import LoaderDiv from './components/LoaderDiv.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    FilterBox,
    LoaderDiv,
    MainContainer,
  },
  data() {
    return {
      dischiList: [],
      flagLoader: false,
      filteredDischi: [],
    }
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      this.dischiList = response.data.response;
      this.filteredDischi = response.data.response;
      this.flagLoader = true;
    });
  },
  methods: {
    // FILTRO PER GENERE -----------------------
    filterGenre(value) {
      // metodo simile al live-coding 
      this.filteredDischi = this.dischiList.filter((disco) => {
        return disco.genre === value || value === 'All';
      });
    },
    // FILTRO PER ARTISTA
    filterArtist(value) {
      this.filteredDischi = this.dischiList.filter((disco) => {
        return disco.author === value || value === 'All';
      });
    },
    filterType(type) {
      this.filteredDischi.forEach((disco) => {
        if (type === Object.keys(disco)) {
          alert('fatto');
        }
      });
    }
  }
}
</script>

<style lang="scss">
  @import './style/app.scss';
</style>


