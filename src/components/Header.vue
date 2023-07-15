<template>
    <header>
     <h1>{{ title }} {{ showAddTask }}</h1>
     <Button @toggle-add-task="$emit('toggle-add-task')" :text=" showAddTask ? 'Close' : 'Add Task ' " :backcolor=" showAddTask ? 'red' : 'green' " />
      
    </header>
</template>

<script>

import Button from './UI/Button.vue';
    export default {
    
    props: {
        title: {
            typeof: String,
            default: "Salom dunyo",   
            },
         showAddTask :Boolean
    },
    components: {
            Button,
    },
    methods: {
        
        }
}

</script>

<style lang="css" scoped>
header{
    display: flex;
    align-items: center;
    justify-content: space-between;
}

</style>