<template>
    <div id="removeSong">
        <p> {{ song }} </p>
        <p> {{ artist }} </p>
        <button v-on:click="remove"> Remove </button>
    </div>
</template>

<script>
export default {
    name: 'Playsong',
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
    remove() {
        //console.log(this.song);
        this.$emit("removePlaysong", this.song , this.artist);
    }
    }
}
</script>

<style scoped>
#removeSong {
     border: 1px solid;
  padding: 10px;
  box-shadow: 5px 10px #888888;
}
</style>