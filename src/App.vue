<template>
<div>
  <div>
    <h1 class="title">TO-DO List</h1>  
      <input 
        type="text" 
        placeholder="Create new task"
        v-model="task"
      >
      <button @click="saveTask(task)" v-if="tasks.length <= 10">Save</button>
    </div>
    <div>
      <div  
        class="noActive"      
        v-for="(item, index) in tasks" :key="index"
        @click="item.status = !item.status"
        :class="{ status: item.status }"
      >
        {{item.taskToDo}} 
        <button @click="delTask(index)">Delete</button>
      </div> 
    </div>
  </div>
</template>

<script>
  export default {
    name: "App",
    data() {
      return {        
        task: "",
        tasks: [
          {taskToDo: 'FIRST TASK', status: false},
          {taskToDo: 'SECOND TASK', status: false},
          {taskToDo: 'THIRHT TASK', status: false},
        ]                   
      }
    },
    methods: {
      saveTask(task) { 
        let a = { taskToDo: task, status: false}      
        this.tasks.push(a);
        return this.tasks;
      },
      delTask(index){
          this.tasks.splice(index, 1);
          //delete this.tasks[index];
          return this.tasks;
      }
    }
  }
</script>

<style>
.title {
  color: red;
}
.noActive{
  color: red;
}
.status{
  color: green;  
}
</style>