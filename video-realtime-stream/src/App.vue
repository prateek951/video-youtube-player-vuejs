<template>
    <div class="container-fluid">
        <SearchBar @termChange="onTermChange"/>
        <VideoList :videos="videos"/>
    </div>
</template>


<script>
import axios from 'axios';
import SearchBar from '@/components/SearchBar';
import VideoList from '@/components/VideoList';
const API_KEY = 'AIzaSyD8iIdw_qPQGPYkMwks2AKE7PruULQlSIE';

export default {
    name: 'App',
    data(){
        return{
            videos: []
        }
    },
    components: {
        SearchBar,
        VideoList
    },
    methods: {
        onTermChange(searchTerm){
            axios.get('https://www.googleapis.com/youtube/v3/search',{
                params: {
                    key: API_KEY,
                    type: 'video',
                    part: 'snippet',
                    q: searchTerm
                }
            })
            .then(response => {
                this.videos = response.data.items
            });
        }
    }   
}
</script>


<style scoped>
    
</style>