<template>
  <div id="app">
    <Header @filtrare="prova" />
    <Main :musics = exporta />
    
  </div>
</template>

<script>

import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  created() {
    this.card()
  },
  computed : {
    exporta() {
      return this.musics.filter((type) => {
        return type.genre.includes(this.decisionee)
      })
    },
  },
  data() {
    return {
      musics : [],
      decisionee : '',
    }
  },
  methods: {
    prova(decision) {
      this.decisionee = decision;
    },
    card () {
        const axios = require('axios');
        
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (response) => {
            // handle success
            this.musics = response.data.response;
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        })
        .then(function () {
            // always executed
        });
        
    }
  }
}
</script>

<style lang="scss">
* {
  margin: 0%;
  padding: 0%;
  box-sizing: border-box;
}

#app {
  height: 100vh;
}
</style>
