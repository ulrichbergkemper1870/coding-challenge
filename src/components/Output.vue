<template>
  <table>
    <thead>
      <tr>
        <th>Index</th>
        <th>Text value</th>
        <th>Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="todo in todos" :key="todo.id">
         <td> {{ todo.id }}</td>
        <td> {{ todo.text }}</td>
        <td><button @click="removeTodo(todo)">remove</button></td>
     
    
    </tr>
     
    </tbody>
  </table>
</template>

<script type="ts">
let id = 0

export default {
   data() {
    return {
      newTodo: '',
      todos: [
        { id: id++, text: 'Learn HTML' },
        { id: id++, text: 'Learn JavaScript' },
        { id: id++, text: 'Learn Vue' }
      ]
    }
  },
  methods: {
     addTodo() {
      this.todos.push({ id: id++, text: this.newTodo })
      this.newTodo = ''
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo)
    }
  }
}
  props: {
    // add optional props here
  },
  setup() {
    // setup component
    return {};
  },
};
</script>
