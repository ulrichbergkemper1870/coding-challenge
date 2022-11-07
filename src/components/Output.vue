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

<style>
.table-list {
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  border-radius: 10px;
  padding: 8px 12px;
  box-sizing: border-box;
}

.table--btn__remove {
  background: none;
  color: red;
  border: none;
  cursor: pointer;
}
</style>

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
      <tr v-for="(item, index) in list" class="table-list" :key="`${item}-${index}`">
        <td>{{ item && index }}</td>
        <td>{{ item && item }}</td>
        <td v-if="item">
          <button @click="handleDelete(index)" class="table--btn__remove">
            {{ REMOVE_TEXT }}
          </button>
        </td>
      </tr>
    </tbody>
  </table>
</template>
