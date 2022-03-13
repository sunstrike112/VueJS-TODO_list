<template>
  <div>
    <div id="app">
      <p>First Component VueJS</p>
      <Header />
      <Todo />
    </div>
  </div>
</template>
<script>
import Header from "./components/Header.vue";
import Todo from "./components/Todo.vue";

export default {
  name: "App",
  components: {
    Header,
    Todo
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial sans-serif;
}
</style>
