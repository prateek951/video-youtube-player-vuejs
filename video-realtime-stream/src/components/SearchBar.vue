<template>
    <div>
        <input type="text" 
        placeholder="Search the video"
        @input="onInput"
        v-model="video"/>
    </div>
</template>

<script>
export default {
    name:'SearchBar',
    data(){
        return{
            video: ''
        }
    },
    methods: {
        onInput(e){
            console.log(e.target.value);
        }
    }

}
</script>


<style scoped> 
    
</style>