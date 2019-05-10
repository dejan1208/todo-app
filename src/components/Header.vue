<template>
  <div>
   <header>
     <img alt="Vue logo" src="../assets/logo.png">
     <h1>Todo List</h1>
   </header>
  </div>
</template>

<script>
export default {
  name: 'Header',
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header{
  color: #A9A9A9;
  background: white;
  padding: 0.5rem;
  display: grid;
  grid-template-columns: 20% 80%;
}


header h1{
  background:  	#696969;
  text-align: center;
}
</style>