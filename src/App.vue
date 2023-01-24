<template>
  <section class="todoapp">
    <header class="header">
      <h1>Tarefas</h1>
    </header>
    <input-Task @newTask="addTask"></input-Task>
    <tasklist :todo-list="tasks"></tasklist>
  </section>
</template>

<script>
import InputTask from './components/InputTask.vue'
import Tasklist from './components/TaskList.vue'

export default {
  name: 'App',
  components: {
    InputTask,
    Tasklist
  },
  data () {
    return {
      tasks: []
    }
  },
  methods: {
    addTask (task) {
      this.tasks.push(task)
    }
  }

}

</script>

<style>
</style>
