<template>
  <div class="home">
    <YouTubePlayer />
    <Playlist />
    <Banner />
  </div>
</template>

<script>
import YouTubePlayer from '../components/YouTubePlayer.vue';
import Playlist from '../components/Playlist.vue';
import Banner from '@/components/Banner.vue';


export default {
  name: 'HomeView',
  components: {
    Navigation,
    YouTubePlayer,
    Playlist,
    Banner
}
}
</script>
