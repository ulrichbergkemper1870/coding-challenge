<script lang="ts" setup>
import Input from "@/components/Input.vue";
import Output from "@/components/Output.vue";
import { computed, ref } from "vue";

const input = ref("");
const list = ref(["hello", "world"]);

const disableAddButton = computed(() => {
  return list.value.length > 10;
})

const handleAdd = input => {
  list.value.push(input);
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
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
  min-height: 100vh;
}
</style>

<template>
  <h1>Coding Challenge</h1>
  <Input :input="input" @handleAdd="handleAdd" :disableAddButton="disableAddButton" />
  <Output :list="list" @handleDelete="handleDelete" />
</template>
