<template>
<div class="carousel-wrapper">
    <carousel :settings="settings" :breakpoints="breakpoints">
    <slide v-for="video in videos" :key="video.id">
        <a :href="'https://www.youtube.com/embed/' + video.snippet.resourceId.videoId" target="_blank">
            <img :src="video.snippet.thumbnails.medium.url" alt="video.snippet.title" class="slide-image"/>
        </a>
     
    </slide>

    <template #addons>
      <navigation />
      <pagination />
    </template>
    </carousel>
</div>  


</template>

<script>
    import 'vue3-carousel/dist/carousel.css';
    import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

    export default {
        name: 'Carrousel',
        props: ['videos'],
        components: { 
            Carousel,
            Slide,
            Pagination,
            Navigation
        },
        data(){
            return{
                settings: {
                    itemsToShow: 1,
                    snapAlign: 'center',
                    },
                    // breakpoints are mobile first
                    // any settings not specified will fallback to the carousel settings
                    breakpoints: {
                    // 700px and up
                    700: {
                        itemsToShow: 2.5,
                        snapAlign: 'center',
                    },
                    // 1024 and up
                    1024: {
                        itemsToShow: 3,
                        snapAlign: 'start',
                    },
                }
            }
        }
    }
</script>

<style>
.carousel-wrapper{
    max-width: 800px;
    margin: 0 auto;
}
.slide-image{
    max-width: 100%;
    width: 100%;
    position: relative;
}

.slide-image:after{
    content: 'WATCH NOW';
    position: absolute;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.3);
    border: 2px solid red;
}

.slide-image:hover:after{
    opacity: 1;
}

.carousel__pagination-button{
    background: #dca890;
}

.carousel__prev, .carousel__next, .carousel__pagination-button--active{
    background: #E2703A;
}


</style>