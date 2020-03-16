<template>
  <div>
    <div v-for="song in songs" v-bind:key="song.title">
      <Song v-bind:song="song.title" v-bind:artist="song.artist" @addPlaylist="pass" />
    </div>
  </div>
</template>

<script>
import Song from "./Song";

export default {
  name: "Songlist",
  components: {
    Song
  },
  props: {
    songs: Array
  },
  methods: {
    pass (song, artist) { 
      //console.log(song);
      //console.log(artist);
      this.$emit("passData", song , artist);
    }
}
};
</script>

<style scoped>
</style>