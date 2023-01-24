<template>
  <div>
    <input class="new-todo" v-on:keyup.enter="addTask" placeholder="O que precisa ser feito?" />
  </div>
</template>

<script>
import { Task } from '../models/Task'
export default {
  methods: {
    addTask ($event) {
      let task = new Task()
      let value = $event.target.value
      task.completed = false
      task.title = value
      this.$emit('newTask', task)
      $event.target.value = ''
    }
  }
}
</script>

<style>
</style>
