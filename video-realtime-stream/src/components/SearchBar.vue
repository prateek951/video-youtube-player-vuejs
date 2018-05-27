<template>
    <div>
        <input type="text" placeholder="Search Video"
        @input="onInput"
        v-model="video">
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
            this.$emit('termChange',e.target.value)
        }
    }

}
</script>


<style scoped> 
    
</style>