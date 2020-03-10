<template>
<div class="wrapper">
  <div id="app">
    <h1>{{title}}</h1>
    <input type="text" placeholder="Add todo..." v-on:keyup.enter="addTodo" />
    <ul>
      <li
        v-for="(todo, index) in todos"
        v-bind:key="index"
        v-on:click="todo.isCompleted = !todo.isCompleted"
        :class="{ strikeThrough: todo.isCompleted }"
      >{{todo.item}}
      <button class="nes-btn is-error padding">X</button>
      </li>
    </ul>
  </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    title: "Lovas Todos",
    todos: [
      { item: "Drink coffee", isCompleted: false, id: Date.now()},
      { item: "Code", isCompleted: false, id: Date.now() },
      { item: "Cry", isCompleted: false, id: Date.now() },
      { item: "Repeat", isCompleted: false, id: Date.now() }
    ]
  }),

  computed: {},

  methods: {
    isDone() {
      this.isDone = !this.isDone;
    },

    addTodo(event) {
      const item = event.target.value;
      this.todos.push({ item, isCompleted: false, id: Date.now() });
      event.target.value = "";
    },

    removeTodo(){

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

.nes-btn {

  border: none;
  color: #ffa2d0;
  font-size: 1rem;
  background: #222;
}


.nes-btn:hover {
  cursor:pointer;
}
</style>
