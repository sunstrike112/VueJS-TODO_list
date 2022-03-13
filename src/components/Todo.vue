<template>
  <AddTodo @add-todo="addTodo" />
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
import {v4 as uuidv4} from "uuid"

import TodoItem from "./TodoItem.vue"
import AddTodo from "./AddTodo.vue"

export default {
  name: "TodoCompoment",
  components: {
    TodoItem,
    AddTodo,
  },
  setup() {
    const todos = ref([
      {
        id: uuidv4(),
        title: "Learn Vue",
        completed: false,
      },
      {
        id: uuidv4(),
        title: "Learn Vuex",
        completed: false,
      },
      {
        id: uuidv4(),
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

    const addTodo = (newTodo) => {
      console.log(newTodo)
      todos.value.push(newTodo)
    }

    return {
      todos,
      markCompleted,
      deleteTodo,
      addTodo
    }
  },
}
</script>

<style></style>
