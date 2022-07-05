<template>
  <div class="main-container">
    <div class="container">
      <h1>ToDo App</h1>
      <hr />
      <label for="todoText"></label>
      <input @keydown.enter="addNewTodo" type="text" id="todoText" placeholder="bir şeyler yaz.." />
      <ul>
        <li v-for="todoItem in todoList" :key="todoItem.id">
          <span> {{ todoItem.text }} </span> 
          <button @click="delteItem(todoItem)">Sil</button>
        </li>
      </ul>
      <small> {{ todoList.length }} adet todo var</small>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      todoList : [
        {id : 1, text : "bootcamp1"},
        {id : 2, text : "bootcamp2"},
        {id : 3, text : "bootcamp3"},
      ]
    }
  },
  
  methods : {
    delteItem(todoItem) {
      this.todoList = this.todoList.filter((t) => t != todoItem);
    },
    addNewTodo(event) {
       this.todoList.push({
        id : new Date().getTime(),
        text : event.target.value
       });
    }
  }

};
</script>
