<template>
    <div>
        <SearchBar @termChange="onTermChange"/>  
    </div>
</template>


<script>
import axios from 'axios';
import SearchBar from '@/components/SearchBar';
const API_KEY = 'AIzaSyD8iIdw_qPQGPYkMwks2AKE7PruULQlSIE';

export default {
    name: 'App',
    components: {
        SearchBar
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
            .then(response => console.log(response))
        }
    }   
}
</script>


<style scoped>
    
</style>