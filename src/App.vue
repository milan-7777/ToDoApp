<template>
  <div class="ToDoApp">
    <h1>ToDo App</h1>
    <div class="ToDos">
      <NewToDo @newToDo="addToDo"/>
      <ToDoList :tasks="tasks" @removeToDo="deleteToDo"/>
    </div>
  </div>

</template>

<script setup>
  import {ref} from 'vue'
  import NewToDo from '@/components/NewToDo.vue'
  import ToDoList from '@/components/ToDoList.vue'

  let tasks = ref([])

  function addToDo(todo) {
    tasks.value.push(todo)
  }

  function deleteToDo(todo) {
    tasks.value.splice(tasks.value.indexOf(todo), 1)
  }
</script>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
  background-color: rgb(47, 52, 58);
  color: #fff;
  font-family: Helvetica,Arial,sans-serif;
}
.ToDoApp {
  margin: 0 auto;
  width: 700px;
  background-color: rgb(47, 52, 58);
  display: flex;
  flex-direction: column;
}

h1 {
  text-align: center;
  margin-bottom: 30px;
  margin-top: 30px;
}

.ToDos {
  display: block;
  margin: 0 auto;
  width: 700px;
}
</style>