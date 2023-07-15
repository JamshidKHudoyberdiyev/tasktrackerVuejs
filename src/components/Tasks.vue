<template>
    <div class="tasks">
        <Task @task-reminder="$emit('task-reminder1',task.id)" @delete-task="$emit('delete-task',task.id)" v-for='task in tasks' :key='task.id' :task="task"/>
    </div>
</template>

<script>
import Task from './Task.vue';
export default {
    props: {
            tasks :Array
    },
        components: {
            Task
    },
    methods: {
        dd(id) {
        console.log(id);
       }
    },
    // emits:['delete-task']
}
    
</script>

<style lang="css" scoped>
.tasks{
    display: flex;
    flex-direction: column;
    gap:10px
}

</style>