<template>
    <button @click="$emit('toggle-add-task')" :style='{backgroundColor:backcolor}' class="btn">
      {{ text }}
    </button>
</template>

<script>
    export default {
    props: {
            text: {
            typeof: String,
            default:"BTN"
            },
            backcolor:String
    },
    methods: {
        
            
        }
    }
</script>

<style lang="css" scoped>

.btn{
    border-radius:3px;
    padding: 10px 20px; 
    background-color: black;
    color: white;
    border: none;
    outline: none;
    cursor: pointer;
}

</style>