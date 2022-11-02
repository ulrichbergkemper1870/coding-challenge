<template>
  <h1>Coding Challenge</h1>
  <Input />
  <Output />
</template>

<script type="ts">
import Input from "@/components/Input.vue";
import Output from "@/components/Output.vue";

export default {
  components: {
    Input,
    Output,
  },
  setup() {
    return {};
  },
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
