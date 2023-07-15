<template>
  <div class="app">
    <Header @toggle-add-task="toggleaddtask" :showAddTask="showAddTask"   title="Task Tracker" />
    <div v-show="showAddTask">
      <AddTask   @add-task="addTask" />
    </div>
    <Tasks @task-reminder1="taskReminder" :tasks ='tasks'  @delete-task="deletTasks" />
  </div>
</template>

<script>
import AddTask from './components/AddTask.vue'
import Header from './components/Header.vue';
import Tasks from './components/Tasks.vue';
export default {

  data() {
    return {
      tasks: [],
      showAddTask:false
    }
  },

 

  created() {
    this.tasks = [
      {
        id: 1,
        text: "reading 10 minit",
        day: "all day",
        reminder:true
      },
      {
        id: 2,
        text: "writing 20 minit",
        day: "twice a day",
        reminder:true
      },{
        id: 3,
        text: " speacking 40 minit",
        day: "all day and all month",
        reminder:false
      }
    ]
  },
  components: {
    Header,
    Tasks,
    AddTask
  },

   methods: {

    toggleaddtask() {
     
      this.showAddTask =!this.showAddTask 
    },
     addTask(task) {
       this.tasks = [...this.tasks,task]
    }
    ,
    deletTasks(id) {
      if (confirm("Are you sure?")) {
        this.tasks = this.tasks.filter(task => task.id != id)
      }
    },
    taskReminder(id) {
      this.tasks=this.tasks.map(task=> task.id ==id ? {...task,reminder:!task.reminder}:task)

      // console.log(this.tasks.id);
    }
  },
  }
</script>

<style lang="css" scoped>
.app{
  padding: 20px;
  margin: 0 auto;
  width: 50%;
  min-height: 400px;
  border: 1px solid black;
}
</style>