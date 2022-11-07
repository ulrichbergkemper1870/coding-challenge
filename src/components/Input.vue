<script lang="ts" setup>
const ADD_TEXT = "Add";
const emit = defineEmits(["handleAdd"]);

defineProps({
  input: String,
  disableAddButton: Boolean
});

const handleAdd = input => {
  emit("handleAdd", input);
};
</script>

<template>
  <form @submit.prevent="handleAdd(input)">
    <input v-model="input" :input="input" type="text" name="input" />
    <button :disabled="disableAddButton">{{ ADD_TEXT }}</button>
  </form>
</template>
