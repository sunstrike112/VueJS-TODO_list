<template>
  <TodoItem
    v-for="todo in todos"
    v-bind:key="todo.id"
    v-bind:todoProps="todo"
  />
</template>

<script>
import { ref } from "vue"

import TodoItem from "./TodoItem.vue"

export default {
  name: "TodoCompoment",
  components: {
    TodoItem,
  },
  setup() {
    const todos = ref([
      {
        id: 1,
        title: "Learn Vue",
        completed: true,
      },
      {
        id: 2,
        title: "Learn Vuex",
        completed: false,
      },
      {
        id: 3,
        title: "Learn Vue Router",
        completed: false,
      },
    ])
    return {
      todos,
    }
  },
}
</script>

<style></style>
