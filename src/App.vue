<template>
  <div>
    <input v-model="currentTodo" @keydown.enter="addTodo()" placeholder="Add a new Task">
    <ul class="todos">
      <li v-for="(todo, index) in todos" :key="todo.id">
        <input class="completedCheck" type="checkbox" v-model="todo.completed">
        <span class="todoLabel" :class="{completed: todo.completed}">
          {{ todo.label }}
        </span>  
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      currentTodo: ''
    };
  },
  methods: {
    addTodo() {
      this.todos.push({id: this.todos.length, label: this.currentTodo, completed: false});
      this.currentTodo = '';
    }
  }
};
</script>

<style>
.completedCheck {
  float: left;
}
</style>
