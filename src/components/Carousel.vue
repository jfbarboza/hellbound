<template>

<Swiper 
    :modules="modules"
    :slides-per-view="4"
    :space-between="10"
    navigation
    :pagination="{ clickable: true }"
    :scrollbar="{ draggable: true }"
    @swiper="onSwiper"
    @slideChange="onSlideChange">
    <SwiperSlide v-for="video in videos" :key="video.id">
         <a :href="'https://www.youtube.com/embed/' + video.snippet.resourceId.videoId" target="_blank">
            <img :src="video.snippet.thumbnails.medium.url" alt="video.snippet.title" class="slide-image"/>
        </a>
    </SwiperSlide>
    <!-- <swiper-slide>Slide 1</swiper-slide>
    <swiper-slide>Slide 2</swiper-slide>
    <swiper-slide>Slide 3</swiper-slide> -->
</Swiper>
  
</template>

<script>

// import Swiper core and required modules
  import { Navigation, Pagination, Scrollbar, A11y } from 'swiper';

  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css';
  import 'swiper/css/navigation';
  import 'swiper/css/pagination';
  import 'swiper/css/scrollbar';

  // Import Swiper styles
  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    props:['videos'],
    setup() {
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
        modules: [Navigation, Pagination, Scrollbar, A11y],
      };
    },
  };
</script>

<style>

</style>