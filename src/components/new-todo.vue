<template>
    <div class="todo-new">
        <form action="">
            <input type="text" v-model="titleTodo" placeholder="Nouvelle tâche...">
            <button @click="NewTodo()"><i class="fas fa-plus-circle"></i></button>
        </form>
    </div>
</template>




<script>
export default {
    name: 'NewTodo',

    data(){
        return{
            titleTodo : "",
        }
    },

    methods:{

        NewTodo() {

            if(this.titleTodo != "") {
                this.$emit('sendTodo', this.titleTodo), console.log(this.titleTodo);
                this.titleTodo = ""
            }
        }
    }


}


</script>





<style scoped>
.todo-new{
margin-top: 20px;
width: 30%;
margin-left: 35%;
height: 50px;
border-bottom: 3px solid rgb(6, 213, 213);
}

.todo-new input{
border: none;
font-size: 20px;
text-align: center;
}

.todo-new button{
border: none;
background-color: white;
cursor: pointer;
}

.todo-new i{
color: rgb(6, 213, 213);
font-size: 30px;
}

</style>