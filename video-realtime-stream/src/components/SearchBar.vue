<template>
    <div class="jumbotron">
        <input type="text" placeholder="Search Video"
        @input="onInput"
        v-model="video"
        class="form-control">
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
    input{
        width: 75%;
    }
    div{
        text-align:center;
        margin-top: 20px;
    }
    
</style>