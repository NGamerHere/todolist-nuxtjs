<script setup >
import '../assets/css/main.css'
</script>
<template>
  <div class="mt-3 text-center" >
    <h1>todolist</h1>
    <ul class="list-inside">
      <li v-for="(item,index) in todos" :key="index" class="list-item my-2 "  >
        {{ item }} <button @click="deleteTask" class="p-0.5 bg-red-500 rounded-md" >delete</button>
      </li>
    </ul>
    <div class="mt-3"  >
      <input type="text"  v-model="newTodos" class="border-2 border-gray-600 rounded p-0.5 "  @keyup.enter="addTask" />
      <button @click="addTask" class="border-2 border-black ps-2 pe-2 pt-0.5 pb-0.5 rounded-md "  > Add task </button>
    </div>
  </div>

</template>

<script>
export default {
  name: "Todolist",
  data(){
    return {
      todos:[ 'sleep' ],
      newTodos:''
    }
  },methods:{
    addTask(){
      this.todos.push(this.newTodos);
      this.newTodos='';
    },deleteTask(index){
      this.todos.splice(index,1);
    }
  }
}
</script>
