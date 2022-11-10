<template>
  <h1>Coding Challenge</h1>
  <Input  @todo-added="addTodo" v-bind:totalItems="totalItems"/>
  <Output v-bind:todos="todos" @todo-deleted="removeTodo" />
</template>

<script type="ts">
import Input from "@/components/Input.vue";
import Output from "@/components/Output.vue";
let id = 0
export default {
  components: {
    Input ,
    Output,
  },
  data() {
    return {
  
      todos: [
        { id: id++, text: 'Example' },
      
      ]
    }
  },
  methods: {
   
     addTodo(text) {
      this.todos.push({ id: id++, text: text })
      this.newTodo = ''
    },
    removeTodo(id) {
      const itemIndex = this.todos.findIndex(item => item.id === id);
      this.todos.splice(itemIndex, 1);
     
      console.log(id);
    }
  },
  setup() {
    return {};
  },
  computed: {
    totalItems() {
     return this.todos.length;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
