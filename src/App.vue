<template>
  <div>
    <NavBar />
    <div class="container mt-3 mb-1">
      <TodoList />
    </div>
    <Footer class="footer" />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import NavBar from './components/layouts/NavBar'
import Footer from './components/layouts/Footer'

export default {
  name: 'app',
  components: {
    TodoList,
    NavBar,
    Footer
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.footer {
  display: block;
  width: 100%;
  position: fixed;
  bottom: 0;
}
</style>
