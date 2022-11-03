<template>
  <form @submit.prevent="onAdd">
    <input type="text" name="textinput" v-model="inputModel" />
    <button type="submit" :disabled="isAddDisabled" v-on:keyup.enter="onAdd">
      Add
    </button>
  </form>
</template>

<script lang="ts">
import { ref } from "vue";

export default {
  props: {
    isAddDisabled: Boolean,
  },
  setup(_, { emit }) {
    const inputModel = ref("");
    const onAdd = () => {
      if (inputModel.value) {
        emit("add-to-list", inputModel.value);
        inputModel.value = "";
      }
    };
    return {
      inputModel,
      onAdd,
    };
  },
};
</script>
