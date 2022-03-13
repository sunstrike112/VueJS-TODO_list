<template>
  <TodoItem
    v-for="todo in todos"
    :key="todo.id"
    :todoProps="todo"
    @item-completed="markCompleted"
    @delete-item="deleteTodo"
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
        completed: false,
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

    const markCompleted = (id) => {
      todos.value = todos.value.map((todo) => {
        if (todo.id === id) todo.completed = !todo.completed
        return todo
      })
    }

    const deleteTodo = (id) => {
      todos.value = todos.value.filter((todo) => todo.id !== id)
    }

    return {
      todos,
      markCompleted,
      deleteTodo,
    }
  },
}
</script>

<style></style>
