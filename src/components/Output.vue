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
    
      <tr v-for="(todo, x) in todos" :key="x">
        <td>{{todo.id}}</td>
        <td>{{todo.text}}</td>
        <td><button @click="deleteToDo(todo.id)">remove</button></td>
      </tr>
    </tbody>
  </table>
</template>

<script type="ts">
export default {
  methods: {
    deleteToDo(id) {
      this.$emit('todo-deleted', id);
    }},
  props: {
    todos:{
      type: String

    }
    
    // add optional props here
  },
  setup() {
    // setup component
    return {};
  },
};

</script>
