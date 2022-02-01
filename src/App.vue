<template>
  <div id="app">
    <header-box />
    <loader-div v-if="!flagLoader" />
    <main-container v-else :dischiList="dischiList"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import MainContainer from './components/MainContainer.vue'
import LoaderDiv from './components/LoaderDiv.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    MainContainer,
    LoaderDiv,
  },
  data() {
    return {
      dischiList: [],
      flagLoader: false,
    }
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      this.dischiList = response.data.response;
      this.flagLoader = true;
    });
  }
}
</script>

<style lang="scss">
  @import './style/app.scss';
</style>


