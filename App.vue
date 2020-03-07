<template>
  <div id="app">
    <h1>{{title}}</h1>
    <input type="text" placeholder="Add todo..." v-on:keyup.enter="addTodo" />

    <ul>
      <li
        v-for="(todo, index) in todos"
        v-bind:key="index"
        v-on:click="todo.isCompleted = !todo.isCompleted"
        :class="{ strikeThrough: todo.isCompleted }"
      >{{todo.item}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  data: () => ({
    title: "Lovas Todos",
    todos: [
      { item: "Drink coffee", isCompleted: false },
      { item: "Code", isCompleted: false },
      { item: "Cry", isCompleted: false },
      { item: "Repeat", isCompleted: false }
    ]
  }),

  computed: {},

  methods: {
    isDone() {
      this.isDone = !this.isDone;
    },

    addTodo(event) {
      const item = event.target.value;
      this.todos.push({ item, isCompleted: false });
      event.target.value = "";
    }
  }
};
</script>


<style>
#app {
  font-family: courier, monospace;
}

h1 {
  font-family: "press start 2p";
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
}

body {
  background-color: #ffa2d0;
}

li:hover {
  cursor: pointer;
}
</style>
