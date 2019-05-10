<template>
  <div id="app">
    <Header />
    <Add v-on:addTodo="addTodo"/>
    <Todo v-bind:todos="todos" v-on:delete="deleteTodo"/>
    
  </div>
</template>

<script>
// Import files from components
import Header from './components/Header';
import Todo from './components/Todo';
import Add from './components/Add';

// Install and import axios
import axios from 'axios';


export default {
  name: 'app',
  components: {
    Header,
    Todo,
    Add
  },
  data(){
    return{
      todos:[]
    }
  },
  methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(res => this.todos = this.todos = this.todos.filter(todo => todo.id !== id))
        .catch(err => console.log(err));
    },
    addTodo(newTodo){
      const {title, completed} = newTodo;
      axios.post('https://jsonplaceholder.typicode.com/todos', {title, completed})
        .then(res => this.todos = [...this.todos, res.data])
        .catch(err => console.log(err));
    }
  },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then(res => this.todos = res.data)
      .catch(err => console.log(err));
  }
}
</script>

<style>

</style>
