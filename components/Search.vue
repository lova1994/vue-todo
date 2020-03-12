<template>
  <div class="search">
    <!-- <input type="text" placeholder="Add todo..." v-on:keyup.enter="addTodo" /> -->
  </div>
</template>

<script>
export default {
  name: 'Search'
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

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

</style>
