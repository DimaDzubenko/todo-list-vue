<template>
    <div>  
        <h1 class="title mx-sm-3 mb-2">TO-DO List</h1> 
        <form class="form-inline">    
            <div class="form-group mx-sm-3 mb-2">
                <input 
                    class="form-control" 
                    type="text" 
                    placeholder="Enter your task"
                    v-model="saveTask"
                >                
            </div>            
            <button 
                type="button" 
                class="btn btn-primary mb-2" 
                @click="pushTask(saveTask)"
                v-if="todoTasks.length < 10"                
            >
                Save
            </button>
        </form> 
    </div>
</template>

<script>
export default {
    name: "AddTodo",

    data(){
        return{
            saveTask:""
        }
    },

    props:{
        todoTasks: {
            type: Array,
            required: true,
            default: null
        }
    },

    methods:{
        pushTask(saveTask){            
            this.$emit('addTask', saveTask);
        }
    }
}
</script>

<style>
.title {
    color: red;
}
</style>