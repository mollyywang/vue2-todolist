<template>
  <div id="app">
    <h1 class="ui dividing centered header">Vue2 Todolist App</h1>
    <div class='ui three column centered grid'>
      <div class='column'>
        <todo-list v-bind:todos="todos"></todo-list>
        <create-todo v-on:create-todo="createTodo"></create-todo>
      </div>
    </div>
  </div>
</template>

<script>
import sweetalert from 'sweetalert';
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'app',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [{
        title: 'Todo 1',
        project: 'Project 1',
        done: false,
      }, {
        title: 'Todo 2',
        project: 'Project 2',
        done: true,
      }, {
        title: 'Todo 3',
        project: 'Project 3',
        done: false,
      }, {
        title: 'Todo 4',
        project: 'Project 4',
        done: false,
      }],
    };
  },
  methods: {
    createTodo(newTodo) {
      this.todos.push(newTodo);
      sweetalert('Success!', 'To-Do created!', 'success');
    },
  },
};
</script>
