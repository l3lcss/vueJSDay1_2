<template>
  <div id="app">
    <!-- done -->
    <div>Done: {{ done }}</div>
    <!-- not-done -->
    <div>Not Done: {{ notDone }}</div>
    <!-- todo-list -->
    <todo-list :todoList="todoList"></todo-list>
    <new-task @addNewTask="addNewTask"></new-task>
  </div>
</template>

<script>
import NewTask from './components/NewTask'
import TodoList from './components/TodoList'

export default {
  name: 'App',
  data () {
    return {
      todoList: [
        { task: 'ซื้อของ', done: false },
        { task: 'อ่านหนังสือ', done: false }
      ]
    }
  },
  computed: {
    done () {
      return this.todoList.filter(t => t.done).length
    },
    notDone () {
      return this.todoList.filter(t => !t.done).length
    }
  },
  methods: {
    addNewTask (newTask) {
      this.todoList.push({
        task: newTask,
        done: false
      })
      // console.log(newTask)
    }
  },
  components: {
    TodoList,
    NewTask
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>