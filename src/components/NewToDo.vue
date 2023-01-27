

<template>
  <div class="greetings">
    <div class="NewToDo">
      <div class="NewToDo__input">
      <label for="toDoInput">New ToDo</label> <br>
      <input type="text" id="toDoInput" v-model="todo">
    </div>
      <button @click="addToDo">ADD TODO!</button>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue'
const emit = defineEmits(['newToDo'])

let todo = ref('')
function addToDo() {
  emit('newToDo', todo.value)
}
</script>

<style scoped>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
.NewToDo {
  display: flex;
  flex-direction: column;
  gap: 20px;
  text-align: center;
}

input {
  width: 700px;
  height: 40px;
  border-radius: 10px;
  border: 2px solid rgb(83, 88, 94);
  background-color: rgb(47, 52, 58);
  color: #fff;
  padding: 0 5px;
}

button {
  width: 700px;
  height: 40px;
  border-radius: 10px;
  background-color: darkcyan;
  border: none;
}

button:hover {
  background-color: rgb(54, 104, 104);
  cursor: pointer;
}
</style>
