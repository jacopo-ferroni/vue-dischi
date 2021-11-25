<template>
  <div class="back-ground d-flex align-items-center justify-content-center">
        <div class="music-zone d-flex flex-wrap justify-content-center" v-if="musics.length > 0">
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

        <div class="loading" v-else>
            <h2>Loading...</h2>
            <svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="bolt" class="svg-inline--fa fa-bolt fa-w-10" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path fill="currentColor" d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"></path></svg>

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
            console.log(response)
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
    height: 100vh;
    background: #1d2d3c;
    .music-zone {
        width: 1200px;
        .music-box {
            width: calc(100% / 8);
            padding: 5px;
        }
    }
    .loading {
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        h2 {
            color: white;
            margin-bottom: 30px;
            animation: color 1s infinite alternate;
        }
        svg {
            color: white;
            width: 100px;
            animation: scale 1s infinite alternate;
        }
            @keyframes scale {
                from {
                    color: white;
                    }
                to {
                    color: #1ed760;
                    scale: 1.3;
                }
            }
            @keyframes color {
                from {
                    color: white;
                    }
                to {
                    color: #1ed760;
                }
            }
    }
}

</style>