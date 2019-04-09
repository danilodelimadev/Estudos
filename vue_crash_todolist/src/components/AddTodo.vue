<template>
  <div class="flex-auto md-col-6 sm-col-10 mb2 mx-auto margin-todo">
    <form class="flex" @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add Todo...">
      <input type="submit" value="Submit" class="btn">
    </form>
  </div>  
</template>


<script>
//import uuid from 'uuid';
export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      }
      // Send up to parent
      this.$emit('add-todo', newTodo);

      this.title = '';
    }
  }
  }

</script>


<style scoped>

input[type="text"] {
  flex: 3;
  padding: 5px;
}

input[type="submit"] {
  flex: 1;
}

@media (max-width: 768px) 
{
  .margin-todo {
    margin: 0 5px 10px;
  }

  p {
    font-size: .8rem;
  }
}

</style>
