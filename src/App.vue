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

export default {
  name: 'App',
  components: {InputTask}
}
</script>

<style>

</style>
