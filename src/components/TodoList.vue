<template>
  <ul>
    <li v-for="(todo, index) in todoList"
      :key="todo.task">
      {{ todo.task }}
      <button @click="updateToDone(index)" :disabled="todo.done">Done</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['todoList'],
  methods: {
    updateToDone (index) {
      this.todoList[index].done = true
    }
  }
}
</script>