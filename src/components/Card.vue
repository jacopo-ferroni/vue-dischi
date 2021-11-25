<template>
    <div class="music-box2">
        <div class="img">
            <img :src="`${image}`" alt="">
        </div>
        <h5>{{title}}</h5>
        <span class="author">{{author}}</span>
        <span class="year">{{year}}</span>
        <span class="genere">{{genere}}</span>
    </div>
</template>

<script>
export default {
    name : `Card`,
    props : {
        author : String,
        image : String,
        title : String,
        year : String,
        genere : String,
    }
}
</script>

<style scoped lang="scss">
.music-box2 {
    text-align: center;
    background: #2e3a46;
    display: flex;
    height: 100%;
    flex-direction: column;
    align-items: center;
    padding: 20px;
    .img {
        width: 100%;
        height: 110px;
        img {
            width: 100%;
            object-fit: contain;
        }
    }
    h5 {
        font-size: 15px;
        color: white;
        margin-top: 10px;
    }
    .author {
        font-size: 10px;
        color: #757d80;
    }
    .year {
        font-size: 10px;
        color: #757d80;
    }
    .genere {
        font-size: 10px;
        color: white;

    }
}
</style>