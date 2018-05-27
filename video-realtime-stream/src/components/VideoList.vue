<template>
    <ul class="list-group">
       <VideoItem v-for="video in videos" :video="video" :key="video.etag"></VideoItem>
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
     }
}
</script>


<style scoped>

</style>
