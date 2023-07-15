<template>
    <div @dblclick="$emit('task-reminder',task.id)" :class="`${task.reminder ? 'reminder' : ''} task` ">
       <h3>{{ task.text }}</h3>
       <p>{{ task.day }}</p>
       <i @click="$emit('delete-task',task.id)" class="fa-sharp fa-solid fa-circle-xmark" style="color: #e71313;"></i>
    </div>
</template>

<script>
    export default {
    props: {
            task:Object
    }, 
    
    
    }
</script>

<style lang="css" scoped>
.task{
    position: relative;
    background-color: rgb(146, 243, 243);
    padding:5px ;
}
.reminder{
    border-left: 8px solid greenyellow;
}
i{
    position: absolute;
    top: 5px ;
    right: 5px;
    cursor: pointer;
}
</style>