<script lang="ts" setup>
import Input from "@/components/Input.vue";
import Output from "@/components/Output.vue";
import { ref } from "vue";

const input = ref("");
const list = ref(["hello", "world"]);

const handleAdd = e => {
  e.preventDefault();
  list.value.push(input.value);

  console.log("add", input.value, e);
};

const handleDelete = index => {
  delete list.value[index];
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
  display
}
</style>

<template>
  <h1>Coding Challenge</h1>
  <Input :input="input" @handleAdd="handleAdd" />
  <Output :list="list" @handleDelete="handleDelete" />
</template>
