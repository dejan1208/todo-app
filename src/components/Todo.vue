<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" v-on:delete="$emit('delete',todo.id)"/>
    </div>
  </div>
</template>

<script>

import TodoItem from './TodoItem.vue';

export default {
  name: 'Todo',
  components:{
    TodoItem
  },
  props:['todos']
}
</script>

<style>

</style>


