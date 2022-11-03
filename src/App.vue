<template>
  <h1>Coding Challenge</h1>
  <Input @add-to-list="addToList" :is-add-disabled="isAddDisabled" />
  <Output :list="list" @remove-from-list="removeFromList" />
</template>

<script lang="ts">
import { ref, computed } from "vue";
import Input from "@/components/Input.vue";
import Output from "@/components/Output.vue";

export default {
  components: {
    Input,
    Output,
  },
  setup() {
    const list = ref([{ id: Date.now().toString(), value: "Example" }]);

    const addToList = (value) => {
      const newItem = {
        id: Date.now().toString(),
        value,
      };
      list.value.push(newItem);
    };

    const removeFromList = (id) => {
      const indexOfitemToRemove = list.value.findIndex(
        (item) => item.id === id
      );
      list.value.splice(indexOfitemToRemove, 1);
    };

    const isAddDisabled = computed(() => {
      return list.value.length === 10;
    });

    return {
      list,
      addToList,
      removeFromList,
      isAddDisabled,
    };
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
