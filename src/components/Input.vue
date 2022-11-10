<template>
  <form  @submit.prevent="onSubmit">
    <input type="text" name="todotext" id="new-todo-input" v-model.lazy.trim="text" />
    <button type="submit" :disabled="addButton?true:false">Add</button>
  </form>
</template>

<script type="ts">
export default {
  methods: {
    onSubmit() {
      if(this.text === "") {
        return;
      }
      this.$emit('todo-added', this.text);
      this.text = "";
    }
  },
  props:{
    totalItems:{
      type: Number
    }
  },
  data() {
    return {
      text: ""
    };
  },
 
  setup() {
    // setup component
    return {};
  },
  computed: {
    addButton() {
     return this.totalItems>10?true:false;
    }
  }
};
</script>
