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
    display: flex;
    height: 100%;
    flex-direction: column;
    align-items: center;
    .img {
        width: 80%;
        img {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }
        
    }
}
</style>