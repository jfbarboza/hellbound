<template>
<div class="playlist">
    <h2>Previous Show Episodes</h2>
    <Carousel :videos="playlist"/>
</div>
    
</template>

<script>

import Carousel from './Carousel.vue';

export default {

    components: {
        Carousel
    },

    mounted(){
       
            const getYoutube = async () =>{

                const res = await fetch('https://youtube.googleapis.com/youtube/v3/playlistItems?part=snippet&playlistId=PLGl4dDwLVoDdVNWjqZbXzlMg79rJiXmSo&maxResults=50&key=AIzaSyBLuvq3hEqvOj41F4sTX4mNq1HuqR_M6zU', {
                    method: 'GET',
                    headers: {
                        "Accept": "application/json"
                    },
                })
           
                let data = await res.json()
                this.playlist = await data.items

                console.log(this.playlist)

            }

            getYoutube()
    },

    data(){
        return{
            playlist: []
        }
    }

}
</script>

<style>
    .playlist h2{
        font-family: 'League Gothic', sans-serif;
        color: #000;
        letter-spacing: 3px;
        text-decoration: underline;
    }
</style>