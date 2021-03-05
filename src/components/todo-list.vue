<template>
    <div class="todo-list">
        <ul class="todolist">

            <li class="todo" v-for="todo in todotab" :key="todo">

                <input type="checkbox" name="done" id="checkbox" v-model="checked" :key="todo" @click="doneEvent">
                <label :key="todo">{{todo.todoName}}</label>
                <input type="button" name="delete" id="delete" :key="todo" @click="deletEvent(todo)">

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
    deletEvent(check){
 this.$emit('deleteTodo', check)
      }
}
}
</script>





<style scoped>

</style>