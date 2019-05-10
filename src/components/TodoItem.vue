<template>
  <div class="todo-item" v-bind:class="{'completed':todo.completed}">
    <p>
      <input type="checkbox" v-on:change='complete'>
      {{todo.title}}
      <button @click="$emit('delete', todo.id)" class="delete">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods:{
    complete(){
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style scoped>
.todo-item {
  background: black;
  color: white;
}

.delete{
  border: 1px solid red;
  border-radius: 50%;
  background: red;
  margin-left: 5rem;
}

.completed{
  text-decoration: line-through;
}

input[type=checkbox]{
  color: black;
}
</style>



