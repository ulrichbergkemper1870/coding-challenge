<script lang="ts" setup>
const ADD_TEXT = "Add";
const emit = defineEmits(["handleAdd"]);

defineProps({
  input: String
});

const handleAdd = () => {
  emit("handleAdd");
};
</script>

<template>
  <form @submit.prevent="handleAdd">
    <input v-model="input" type="text" name="input" />
    <button>{{ ADD_TEXT }}</button>
  </form>
</template>
