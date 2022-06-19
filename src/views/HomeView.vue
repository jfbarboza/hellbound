<template>
  <div class="home">
    <YouTubePlayer />
    <Playlist />
  </div>
</template>

<script>
import YouTubePlayer from '../components/YouTubePlayer.vue';
import Playlist from '../components/Playlist.vue';


export default {
  name: 'HomeView',
  components: {
    Navigation,
    YouTubePlayer,
    Playlist
}
}
</script>
