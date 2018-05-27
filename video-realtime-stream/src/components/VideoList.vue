<template>
    <ul class="list-group col-md-4">
       <VideoItem @videoSelect="onVideoSelect" v-for="video in videos" :video="video" :key="video.etag"></VideoItem>
    </ul>    
</template>


<script>
import VideoItem from '@/components/VideoItem';
export default {
     name: 'VideoList',
     props:{
         videos: Array
     },
     components:{
         VideoItem
     },
     methods: {
         onVideoSelect(video){
            this.$emit('videoSelect',video);
         }
     }
}
</script>


<style scoped>

</style>
