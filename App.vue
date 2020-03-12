<template>
<div class="wrapper">
  <div id="app">
    <Header title="Lovas Todos" />
      <input type="text" v-model="text" placeholder="Add todo..." 
      v-on:keyup.enter="addTodo()" />
<Todos v-bind:todos="todos"
v-on:del-todo="removeTodo"
/>
  </div>
  </div>
</template>
<script>

import Todos from './components/Todos'
import Header from './components/Header'


export default {
 name: 'App',
  components: {
    Todos,
    Header
  },

  data: () => ({
    title: "Lovas Todos",
    todos: [
      { item: "Drink coffee", isCompleted: false, id: 1},
      { item: "Code", isCompleted: false, id: 2 },
      { item: "Cry", isCompleted: false, id: 3 },
      { item: "Repeat", isCompleted: false, id: 4 }
    ]
  }),

  computed: {},

  props: ["title"],

  methods: {
    isDone() {
      this.isDone = !this.isDone;
    },

    addTodo() {
      const item = this.text;
      this.todos.push({ item, isCompleted: false, id: Date.now() });
      this.text = "";
    },

    removeTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    }
  }
};
</script>


<style>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  color: #ffa2d0;
}

#app {
  font-family: courier, monospace;
}

h1 {
  font-family: "press start 2p";
  font-size: 3rem;
}

.strikeThrough {
  text-decoration: line-through;
}

#normal {
  text-decoration: none;
}

.active {
  background-color: #a2ffb4;
  padding: 3%;
}

.strike {
  text-decoration: line-through;
  transition: 3s;
}

body {
  background-color: #222;
}

li:hover {
  cursor: pointer;
}

input {
  background: #222;
  border:none;
  border-bottom: solid 2px #ffa2d0;
  width: 10rem;
  height: 2rem;
  font-family: 'courier new';
  font-size: 1.3rem;
  color: #ffa2d0;
}

li {
  font-size: 2rem;
}

::placeholder {
  font-family: 'courier new';
  font-size: 1.2rem;
}

.btn {

  border: none;
  color: #ffa2d0;
  font-size: 1rem;
  background: #222;
}


.btn:hover {
  cursor:pointer;
}
</style>
