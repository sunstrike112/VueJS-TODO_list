<template>
  <p :class="['todo-item', todoProps.completed ? 'is-completed' : '']">
    <input type="checkbox" :checked="todoProps.completed" />
    {{ todoProps.title }}
    <button class="delete-btn">Delete</button>
  </p>
</template>

<script>

export default {
  name: "TodoItem",
  props: ["todoProps"],
}
</script>

<style>
.todo-item {
  background-color: #f4f4f4;
  padding: 10px;
  margin: 0;
  border-bottom: 1px solid #ccc;
}

.delete-btn {
  background-color: red;
  border: none;
  color: #fff;
  cursor: pointer;
  font-size: 1.2rem;
  padding: 5px 10px;
  float: right;
}

.is-completed {
  text-decoration: line-through;
}
</style>
