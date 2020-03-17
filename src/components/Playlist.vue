<template>
  <div>
    <div v-for="play in Playlist" v-bind:key="play.title">
      <Playsong v-bind:song="play.title" v-bind:artist="play.artist" @removePlaysong='passData' />
    </div>
  </div>
</template>

<script>
import Playsong from "./Playsong";

export default {
  name: "Playlist",
  components: {
    Playsong
  },
  props: {
    Playlist: Array
  },
  methods: {
    passData (song, artist) { 
      //console.log(song);
      //console.log(artist);
      this.$emit("passSong", song , artist);
    }
}
};
</script>

<style scoped>
</style>