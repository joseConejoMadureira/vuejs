<template>
<ul class="todo-list">
  <transition-group name="fade" >
      <li v-for="todo in sortedTasks"
        class="todo" :key="todo">
      <div class="view">
        <input class="toggle" @click="completeTask(todo)" type="checkbox">
        <label :class="{'todo-completed':todo.completed}" > {{ todo.title }}</label>
      </div>
    </li>
  </transition-group>
</ul>
</template>

<script>
export default {
  props: ['todoList'],
  computed: {
    sortedTasks: {
      get: function () {
        let sorted = this.todoList
        return sorted.sort(function (a, b) {
          if (a.title < b.title) return -1
          if (a.title > b.title) return 1
          return 0
        })
      },
      set: function (novaLista) {
        this.todoList.concat(novaLista)
      }
    }
  },
  methods: {
    completeTask (task) {
      task.completed = !task.completed
    }
  }
}

</script>

<style>
.todo-completed{
    text-decoration: line-through;
}
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to{
  opacity: 0;
}
</style>
