<template>
  <div class="container">
  <h1 class="header">Todo App</h1>
  <div>
    <input class="newTask" type="text" v-model="todo" placeholder="Create New Todo"/>
    <button @click="addTask(todo.id)" class="addTask">Add Task</button>
  </div>
  <div class="Todo" v-for="todo in todos" v-bind:key="todo.id">
    <input type="checkbox" v-model="todo.completed" class="taskCompleted">
    {{ todo.text }}
    <button @click="removeTask(todo.id)" class="removeTask">Delete</button>
  </div>
</div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      todo: "",
      todos: [ 
        {
          id: Math.random(),
          text: "Test for my Todo List",
          completed: true,
          
        },
        {
          id: Math.random(),
          text: "Hello world",
          completed: false,
        }

      ],
    };
  },
  methods: {
    addTask() {
      if (this.todo.length === 0) {
        return;
      } 
      else {
        this.todos.push({
          id: Math.random(),
          text: this.todo,
          completed: false,
        })
      }
    },
    removeTask(todosId) {
      this.todos = this.todos.filter((todo) => todo.id !== todosId);
    },
  },
}
</script>

<style>
@import "/public/style.css";
</style>
