<template>
    <div v-if="video">
        <div>
            <iframe width="560" 
            height="315" 
            :src="computeVideoUrl" 
            frameborder="0" 
            allow="autoplay; encrypted-media" 
            allowfullscreen></iframe>
        </div>
        <div class="details">
           <h4>{{video.snippet.title}}</h4>
           <p class="border-1">{{video.snippet.description}}</p> 
        </div>
    </div>
</template>


<script>
export default {
    name: 'VideoDetail',
    props:['video'],
    computed: {
        computeVideoUrl(){
            const {videoId} = this.video.id;
            return `https://www.youtube.com/embed/${videoId}`;
        }
    }
}
</script>


<style scoped>
    .border-1{
        border: 2px dotted #ddd;
        margin-top: 10px;
        padding: 10px;
        border-radius: 4px; 

    }
</style>