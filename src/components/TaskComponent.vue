<template>
    <h1>To Do App {{fullName}}</h1>
    <input @keyup.enter="addNewTask" ref="txtTask" type="text" v-model="newTask" placeholder="Add a new task">
    <button @click="addNewTask">Add</button>
    <ul>
        <li v-for="(item,index) in todoList" :key="index">
            {{ item }}
            <button id="btnDelete" @click="removeTask(index)">Delete</button>
        </li>
    </ul>
</template>

<script>
export default{
    name:"TaskComponent",
    data(){
        return {
            todoList: [],
            fullName: "Cristiano Ronaldo",
            newTask:""            
        }
    },
    methods:{
        addNewTask(){
            console.log("Aquí se agregará la tarea") 
            this.todoList.push(this.newTask)  
            this.newTask = ""
            this.$refs.txtTask.focus()            
        },
        removeTask(index){
            console.log("El valor de index es: " + index)
            this.todoList.splice(index,1)
        }
    }
}
</script>

<style>
button{
    background-color: green ;
    color: white;
}

button:hover{
    background-color: yellow;
    color: darkgray;
}

#btnDelete{
    background-color: red;
    color: aliceblue;
}
</style>
