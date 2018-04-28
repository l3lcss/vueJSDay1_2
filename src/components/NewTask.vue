<template>
  <div>
    <input type="text" v-model="task">
    <button @click="addNewTask">Add new task</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      task: ''
    }
  },
  methods: {
    addNewTask () {
      this.$emit('addNewTask', this.task)
      this.task = ''
    }
  }
}
</script>