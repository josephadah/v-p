<template>
  <div>
    <h1 class="text-center mb-4">My Todo List</h1>
    <div>
      <AddTodo v-if="!editing" @add-todo="addTodo"/>
      <EditTodo v-if="editing" :todo="selectedTodo" @edit-todo="editTodo" />
      <table class="table">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Title</th>
            <th scope="col"></th>
            <th scope="col"></th>
            <th scope="col"></th>
          </tr>
        </thead>
        <tbody>
          <TodoItem v-for="(todo, index) in todos" 
            :todo="todo" :index="index" :key="todo.id" 
            @toggle-completed="toggleCompleted"
            @edit-todo="editingTodo"
            @delete-todo="deleteTodo"
          />
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'
import AddTodo from './AddTodo'
import EditTodo from './EditTodo'

export default {
  name: 'TodoList',
  props: {
    msg: String
  },
  components: {
    TodoItem,
    AddTodo,
    EditTodo
  },
  data: () => {
    return {
      todos: [
        {id: 1, title: "Go to market", completed: false},
        {id: 2, title: "Wash your clothes completed", completed: false},
        {id: 3, title: "Love Rose the more", completed: true}
      ],
      editing: false,
      selectedTodo: {}
    }
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    },
    toggleCompleted(todo) {
      todo.completed = !todo.completed;
      const index = this.todos.findIndex(t => t.id === todo.id);
      this.todos.splice(index, 1, todo);
    },
    editingTodo(todo) {
      this.selectedTodo = todo;
      this.editing = true;
    },
    editTodo(todo) {
      this.selectedTodo = {};
      this.editing = false;
    },
    deleteTodo(todo) {
      this.todos = this.todos.filter(t => t.id !== todo.id);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
