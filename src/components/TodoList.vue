<template>
    <div class="mx-sm-3 mb-2">    
        <div v-for="(task, indexTask) in tasks" :key="indexTask"> 
            <TodoItem 
                :task="task"
                :indexTask="indexTask"
                @delTaskIndex="delTodoTaskIndex($event)"
            />
        </div>    
    </div>
</template>


<script>

import TodoItem from "@/components/TodoItem.vue";

export default {
    name: "TodoList",

    components:{
        TodoItem
    },

    props:{
        todoTasks: {
            type: Array,
            required: true,
            default: null
        }
    },

    data(){
        return{           
            tasks: this.todoTasks
        }
    },

    methods:{
        delTodoTaskIndex(event){            
            console.log(event);
            this.$emit('delTodoTaskIndex', event);
        }
    }
}
</script>

<style  scoped>

</style>