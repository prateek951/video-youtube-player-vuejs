<template>
    <li class="list-group-item">
        <img :src="thumbnail" alt="">
        {{video.snippet.title}}
    </li>
</template>


<script>
export default {
    props:['video'],
    name: 'VideoItem',
    computed:{
        thumbnail(){
            return this.video.snippet.thumbnails.default.url;
        }
    }
}
</script>

<style scoped>

</style>
