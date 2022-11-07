<script lang="ts" setup>
const emit = defineEmits(["handleDelete"]);
const REMOVE_TEXT = "remove";
const HEADER = {
  index: "Index",
  text: "Text value",
  actions: "Actions"
};

defineProps({
  list: Array
});

const handleDelete = index => {
  emit("handleDelete", index);
};
</script>

<template>
  <table>
    <thead>
      <tr>
        <th>{{ HEADER.index }}</th>
        <th>{{ HEADER.text }}</th>
        <th>{{ HEADER.actions }}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, index) in list">
        <td>{{ item && index }}</td>
        <td>{{ item && item }}</td>
        <td v-if="item">
          <button @click="handleDelete(index)">{{ REMOVE_TEXT }}</button>
        </td>
      </tr>
    </tbody>
  </table>
</template>
