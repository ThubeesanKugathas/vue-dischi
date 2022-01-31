<template>
  <div id="app">
    <header-box />
    <main-container />
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    MainContainer,
  },
  data() {
    return {
      dischiList: []
    }
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      this.dischiList = response.data;
    });
  }
}
</script>

<style lang="scss">
  @import './style/app.scss';

</style>


