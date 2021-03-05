<template>
    <div class="todo-list">
        <ul class="todolist">

            <li class="todo" v-for="todo in todotab" :key="todo">

                <input type="checkbox" name="done" id="checkbox" v-model="checked" :key="todo">
                <label :key="todo">{{todo.todoName}}</label>
                <input type="button" name="delete" id="delete">

            </li>
               
        </ul>
    </div>
</template>




<script>
export default {
    name: 'TodoList'
    
}
</script>





<style scoped>

</style>