<template>
  <div class="home">
    <Navigation />
    <YouTubePlayer />
    <Playlist />
  </div>
</template>

<script>
import Navigation from '@/components/Navigation.vue';
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
