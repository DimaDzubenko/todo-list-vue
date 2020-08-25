<template>
  <div class="container">
    <div class="row justify-content-md-center">
      <div class="col-md-auto">
        <AddTodo
          @addTask="addTodoTask($event)"
          :todoTasks="todoTasks"
        />
        <TodoList 
          :todoTasks="todoTasks"    
          @delTodoTaskIndex="deleteTodoTask($event)"      
        />  
      </div>  
    </div>        
  </div>
</template>

<script>
  import AddTodo from "@/components/AddTodo.vue";
  import TodoList from "@/components/TodoList.vue";
  

  export default {
    name: "App",

    components:{
      // равнозначная запись регистрации компонентов
      AddTodo: AddTodo,
      TodoList     
    },

    data() {
      return{ 
        todoTasks: [
                {todo: 'Task 1', status: false},
                {todo: 'Task 2', status: false},
                {todo: 'Task 3', status: false},
                {todo: 'Task 4', status: false},
                {todo: 'Task 5', status: false}
            ]
      }
    },

    methods:{
      addTodoTask(event){
        let obj = {todo: event, status: false}
        this.todoTasks.push(obj);
      },

      deleteTodoTask(event){
        console.log(event);
        this.todoTasks.splice(event, 1);
      }
    }
  }
</script>

<style>


</style>