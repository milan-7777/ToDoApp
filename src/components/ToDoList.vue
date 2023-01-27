<template>
    <div class="ToDoList">
        <h2>ToDo List</h2>
        <ul>
            <li v-for="task in tasks">
                <div class="ToDoList__Item">
                    <span> {{ task }} </span> 
                    <button @click="$emit('removeToDo', task)">Remove</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script setup>
defineProps({
    tasks: Array
})
  </script>

<style scoped>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

h2 {
    text-align: center;
    margin-top: 30px;
}
.ToDoList__Item {
    display: flex;
    margin-top: 20px;
    border-radius: 10px;
    width: 100%;
    background-color: rgb(47, 52, 58);
    color: #fff;
}

li {
    list-style: none;
    width: 700px;
}

span {
    height: 40px;
    width: 80%;
    border: 2px solid rgb(83, 88, 94);
    border-radius: 10px;
    padding: 10px 5px;
}

button {
    width: 20%;
    height: 40px;
    border-radius: 10px;
    background-color: darkcyan;
    border: none;
    float: right;
}

button:hover {
  background-color: rgb(54, 104, 104);
  cursor: pointer;
}
</style>