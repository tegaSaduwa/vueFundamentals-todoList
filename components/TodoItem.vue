<template>
  <div class="todo-item" :class="{ 'is-complete': todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markedComplete">
      {{ todo.title }}
      <button  @click="$emit('del-todo', todo.id)" class="del">x</button>
      
      </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markedComplete () {
     this.todo.completed = !this.todo.completed; 
    }
  }
}

</script>

<style scoped>

.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #ff0000; 
  color: #fff;
  border:none;
  border-radius: 100%;
  padding: 5px 5px;
  cursor:pointer;
  float:right;
}

</style>


