<template>
  <form @submit='addTodo'>
    <input type="text" v-model="title" name="title" placeholder="Add Todo..." >
    <button><h1>Submit</h1></button>
  </form>
</template>

<script>
export default {
  name: 'Add',
  data() {
    return {
      title: ''
    }
  },
  methods:{
    addTodo(e){
      e.preventDefault();
      const newTodo ={
        title: this.title, 
        completed: false
      }
      this.$emit('addTodo', newTodo);
      this.title = '';
    }
  }
}
</script>

<style scoped>
  form{
    display: flex;
  }
  input[type='text']{
    flex: 3;
    padding: 0.5rem;
  }
  button{
    flex: 9;
    background: green;
    color: white;
  }

</style>


