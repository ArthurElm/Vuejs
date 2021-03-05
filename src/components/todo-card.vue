<template>
    <div class="todo-card">
        <section class="menu">
        <ul>
            <li>{{moment().format('dddd') + " " + moment().format('LL')}}</li>
            <li>{{title}}</li>
            <li :key="todo">{{todotab.length}} tâches</li>
        </ul>
        
        <new-todo @sendTodo="addTodo"/>

        <todo-list :todotab="todotab" @deleteTodo="deleteEvent"/>
        </section>
    </div>
</template>



<script>
import newTodo from './new-todo.vue'
import moment from 'moment'
import TodoList from './todo-list.vue';



export default {
  components: { newTodo, TodoList },
    name: 'TodoCard',
    created: function () {
    this.moment = moment;
    },

    data() {
        return {
            title : "VueJs Tutorial ToDo List",
            todotab:[],

        }
    },

    methods: {
        addTodo(a){
        let todo ={
            todoName : a,
            checked : false
        }
       this.todotab.push(todo);
       //console.log(todotab);
    },
    deleteEvent: function(event) {
  this.todotab.splice(this.todotab.indexOf(event), 1);
    }
    }
}
</script>




<style scoped>
.todo-card{
    width: 70%;
    height: 500px;
    background-color: aliceblue;
    margin-left: 15%;
    border-radius: 21px;
    background-color: white;
}

ul{
width: 100%;
height: 70px;
display: flex;
flex-direction: row;
justify-content: space-around;
-webkit-box-shadow: 0px 5px 3px 0px rgba(0,0,0,0.36);
-moz-box-shadow: 0px 5px 3px 0px rgba(0,0,0,0.36);
box-shadow: 0px 5px 3px 0px rgba(0,0,0,0.36);
}

li{
margin-top: 20px;
font-size: 20px;
font-weight: 600;
}

li:nth-child(2){
color: rgb(6, 213, 213);
}

</style>