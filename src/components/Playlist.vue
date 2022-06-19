<template>
  Playlist
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
                this.playlist = data.items
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

</style>