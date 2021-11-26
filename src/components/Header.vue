<template>
    <div class="header d-flex align-items-center justify-content-between">
        <img src="@/assets/logo.png" alt="">

        <div class="input">
            <select v-model="decisione">
                <option value="" disabled selected hidden>Tutti</option>
                <option value="">Tutti</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>

            <button @click="$emit(`filtrare`, decisione)">Filtra</button>

        </div>
    </div>

</template>

<script>
export default {
name : `Header`,
data() {
    return {
        decisione : '',
    }
},
methods: {
    prova() {
        console.log(this.decisione);
    }
}
}
</script>

<style scoped lang="scss">
.header {
    background: #2e3a46;
    height: 80px;
    top: 0%;
    left: 0%;
    width: 100%;
    img {
        height: 100%;
        padding: 10px;
    }
    .input {
        margin-right: 20px;
        button {
            padding: 5px;
            margin-left: 20px;
            border-radius: 15px;
            border: 2px solid black;
            font-size: 13px;
            background: #1ed760;
        }
    }
}
</style>