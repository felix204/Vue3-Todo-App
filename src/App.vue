<template>
  <div class="main-container">
    <div class="container">
      <h1>ToDo App</h1>
      <hr />
      <AddSection @add-todo="addNewTodo"/>
      <TodoInList @delete-todo-item="deleteItem" :myData="todoList"/>
      <ResultBar :itemCount="todoList.length"/>
      
    </div>
  </div>
</template>

<script>

// Import Area Start
import AddSection from "@/components/AddSection.vue";
import TodoInList from "@/components/TodoInList.vue";
import ResultBar from "./components/ResultBar.vue";

// Import Area End


export default {
  components : {
    AddSection,
    TodoInList,
    ResultBar
},
created() {
  this.todoList = [
        {id : 1, text : "Item1"},
        {id : 2, text : "Item2"},
        {id : 3, text : "Item3"},
        {id : 4, text : "Item4"},
        {id : 5, text : "Item5"},
      ]
},
data(){
    return {
      todoList : []
    }
  },
  
  methods : {
    deleteItem(todoItem) {
      this.todoList = this.todoList.filter((t) => t != todoItem);
    },
    addNewTodo(todo) {
      this.todoList.push({
        id : new Date().getTime(),
        text : todo
      });
    }
  }
};
</script>
