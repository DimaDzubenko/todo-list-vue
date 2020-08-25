<template>
    <div class="form-check">
        
        <label class="form-check-label mb-2" for="defaultCheck1">
            {{todoTask.todo}}
        </label>
        <button 
            type="button" 
            class="btn btn-warning mb-2"
            @click="clickBtnDel()"            
        >
            Delete
        </button>
    </div>
</template>

<script>
export default {
    name: "TodoItem",

    props:{
        task: {
            type: Object,
            required: true,
            default: null
        },

        indexTask: {

        }
    },

    data(){
        return{           
            todoTask: this.task,
            index: this.indexTask
        }
    },

    methods:{
        clickBtnDel(){
            console.log(this.index);            
            this.$emit('delTaskIndex', this.index);
        }
    }
}
</script>

<style  scoped>

</style>