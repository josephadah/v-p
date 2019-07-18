<template>
  <div>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        <TodoItem :todo="todo" />
      </li>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem';

export default {
  name: 'TodoList',
  props: {
    msg: String
  },
  components: {
    TodoItem
  },
  data: () => {
    return {
      todos: [
        {id: 1, title: "Go to market", completed: false},
        {id: 2, title: "Wash your clothes completed", completed: false},
        {id: 3, title: "Love Rose the more", completed: true}
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
