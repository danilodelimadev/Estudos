<template>
<div class="flex-auto">

    <div class="todo-item flex mb2 md-col-6 mx-auto margin-todo" >
     
    <div class="flex-auto items-center" :class="{'is-complete':todo.completed }">
      <p class="flex ml1 items-center">
      <input type="checkbox" @change="markComplete">
      {{ todo.title }}
      </p>
    </div>

    <div class="divider ml2"></div>

    <div class="flex items-center px2">
      <button class="del" @click="$emit('del-todo', todo.id)">X</button>
    </div>
      

  </div>
</div>
<!-- <div class="clearfix mx-auto">
  
</div> -->
</template>


<script>
export default {
  name: "TodoItem",
  props: ["todo"], 
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
}
</script>


<style scoped>

.todo-item {
  background: whitesmoke;
  padding: 10px;
  font-weight: 500;
  font-size: 1rem;
  box-shadow: 0 1px 2px #999;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #f00909;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  box-shadow: 0 1px 2px #999;
}

.del:active {
  box-shadow: none;
  background: #db0808;  
}

.color1 {
  background: cyan;
}

.divider {
 border-left: 2px solid rgba(179, 174, 174, 0.3);
}

input[type="checkbox"] {
    margin-right: 10px;
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
