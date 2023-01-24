<template>
  <section class="todoapp">
    <header class="header">
      <h1>Tarefas</h1>
    </header>
    <input-Task></input-Task>
    <tasklist :todo-list="tasks"></tasklist>
  </section>
</template>

<script>
import InputTask from './components/InputTask.vue'
import Tasklist from './components/TaskList.vue'

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
  components: {
    InputTask,
    Tasklist
  },
  data () {
    return {
      tasks: tasks
    }
  }
}

</script>

<style>
</style>
