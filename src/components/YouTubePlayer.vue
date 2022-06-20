<template>
  <div class="player-wrapper">
     <div class="title">
         <iframe :src="lastVideo.url" frameBorder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
     </div>
  </div>
</template>

<script>
export default {

    beforeMount(){
       
            const getYoutube = async () =>{

                const res = await fetch('https://youtube.googleapis.com/youtube/v3/playlistItems?part=snippet&playlistId=PLGl4dDwLVoDdVNWjqZbXzlMg79rJiXmSo&maxResults=50&key=AIzaSyBLuvq3hEqvOj41F4sTX4mNq1HuqR_M6zU', {
                    method: 'GET',
                    headers: {
                        "Accept": "application/json"
                    },
                })
           
                let data = await res.json()
                console.log(data.items[data.items.length - 1].snippet)
                this.lastVideo.url = `https://www.youtube.com/embed/${data.items[data.items.length - 1].snippet.resourceId.videoId}?&modestbranding=1`


            }

            getYoutube()
    },

   data(){
       return{
           lastVideo: {
               title: null,
               url: null
           }
       }
   }

}
</script>

<style>
 .player-wrapper{
     width: 100%;
     height: calc(100vh - 100px);
     /* background: rgb(251, 249, 243); */
     background: #000;
     padding: 20px;
     display: flex;
     justify-content: center;
     align-items: center;
 }
 .player-wrapper iframe{
     width: 800px;
     height: 600px;
 }

 @media only screen and (max-width: 600px) {

  .player-wrapper{
    display: block;
    height: auto;
  }  
  .player-wrapper iframe {
    width: 90%;
    height: auto;
    display: block;
  }
}
</style>