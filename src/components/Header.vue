<template>
    <div class="header">
        <img src="@/assets/logo.png" alt="">
    </div>

</template>

<script>
export default {
name : `Header`,
}
</script>

<style scopes lang="scss">
.header {
    background: #2e3a46;
    height: 10vh;
    top: 0%;
    left: 0%;
    width: 100%;
    img {
        height: 100%;
        padding: 10px;
    }
}
</style>