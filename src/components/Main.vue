<template>
  <div class="back-ground d-flex align-items-center justify-content-center">
        <div class="music-zone d-flex flex-wrap justify-content-center">
            <div class="music-box" v-for="(music, index) in musics" :key="`music-${index}`">
                <Card 
                :image = music.poster
                :author = music.author
                :title = music.title
                :year = music.year
                :genere = music.genre
                />
            </div>
        </div>
  </div>
</template>

<script>
import Card from '@/components/Card.vue';

export default {
name : `Main`,
components : {
    Card,
},

data() {
    return {
        musics : [],
    }
},

created() {
    this.card()
},

methods : {
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

<style scoped lang="scss">
.back-ground {
    height: 90%;
    background: #1d2d3c;
    .music-zone {
        min-width: 1200px;
        .music-box {
            width: calc(100% / 8);
            border: 1px solid green;
            padding: 5px;
        }
    }
}

</style>