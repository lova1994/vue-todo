<template>
    <div>

   <p v-on:click="todo.isCompleted = !todo.isCompleted"
        :class="{ strikeThrough: todo.isCompleted }">
      {{todo.item}} 
      <button class="btn"   @click="$emit('del-todo', todo.id)"  >X</button>
      </p>
    </div>

</template>


<script>
export default {
    name: "TodoItem",
    props: ["todo"]
}
</script>

<style scoped>

</style>