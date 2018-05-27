<template>
    <li @click="onVideoSelect" class="list-group-item media">
        <img class="mr-3" :src="thumbnail" alt="">
        <div class="media-body">
            {{video.snippet.title}}
        </div>
    </li>
</template>


<script>
export default {
    props:['video'],
    name: 'VideoItem',
    methods: {
        onVideoSelect(){
            this.$emit('videoSelect', this.video);
    }
    },
    computed:{
        thumbnail(){
            return this.video.snippet.thumbnails.default.url;
        }
    }
}
</script>

<style scoped>
    li{
        display: flex;
        cursor:pointer;
    }
    li:hover{
        background:black;
        color:white;
    }
</style>
