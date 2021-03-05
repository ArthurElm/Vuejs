<template>
    <div class="todo-list">
        <ul class="todolist">

            <li class="todo" v-for="todo in todotab" :key="todo">

                <input type="checkbox" name="done" id="checkbox" v-model="checked" :key="todo">
                <label :key="todo">{{todo.todoName}}</label>
                <input type="button" name="delete" id="delete" @click="deletEvent(event)">

            </li>
               
        </ul>
    </div>
</template>




<script>
export default {
    name: 'TodoList',

    props:{
        todotab:{
            type: Array
        }
       
    },
methods: {
    deletEvent(){
 this.$emit('deleteTodo', this.titleTodo)
      }
}
}
</script>





<style scoped>

</style>