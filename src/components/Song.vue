<template>
    <div>
        <p> {{ song }} </p>
        <p> {{ artist }} </p>
        <button v-on:click="add"> Add </button>
    </div>
</template>

<script>
export default {
    name: 'Song',
    props: {
        song: {
            type: String,
            required: true
        },
        artist: {
            type: String,
            required: true
        }
    },
    methods: {
    add() {
        //console.log(this.song);
        this.$emit("addPlaylist", this.song , this.artist);
    }
    }
}
</script>

<style scoped>

</style>