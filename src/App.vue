<template>
 <Songlist :songs="songs" @passData="changeToPlaylist" /> 
</template>

<script>
import Songlist from './components/Songlist.vue'
//import Playlist from './components/Playlist.vue'

export default {
  name: 'App',
  components: {
    Songlist
   // Playlist
  },
  data : function() {
    return { 
      songs: [{title: 'song1', artist: 'artist1'} , {title: 'song2', artist: 'artist2'} ,{title: 'song3', artist: 'artist3'} , {title: 'song4', artist: 'artist4'}],
      playlist: []
  } 
  },
   methods: {
      changeToPlaylist (song, artist) {
        //console.log(this.songs);
        //console.log(artist);
        //console.log(song);
        var i;
         for(i=0; i < this.songs.length; i++) {
           if (this.songs[i].title == song && this.songs[i].artist==artist) {
             this.songs.splice(i,1);
             this.playlist.push(this.songs[i]);  
           }
         }
         //console.log(this.playlist);
        }
      }
  }



</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
