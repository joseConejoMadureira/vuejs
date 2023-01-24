<template>
  <section class="todoapp">
    <header class="header">
      <h1>Tarefas</h1>
      <input-Task></input-Task>
    </header>
  </section>
</template>

<script>
import InputTask from './components/InputTask.vue'
import { Task } from './models/Task'
let tasks = []
let task = new Task()
task.completed = false
task.title = 'tarefa'
tasks.push(task)
tasks.push(task)
tasks.push(task)

export default {
  name: 'App',
  components: {InputTask},
  data () {
    return {
      tasks: tasks
    }
  }
}

</script>

<style>
</style>
