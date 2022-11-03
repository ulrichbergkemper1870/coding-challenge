<template>
  <table>
    <thead>
      <tr>
        <th>Index</th>
        <th>Text value</th>
        <th>Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, idx) in list" :key="`item-${item.id}`">
        <td>{{ idx + 1 }}</td>
        <td>{{ item.value }}</td>
        <td>
          <button @click="$emit('remove-from-list', item.id)">remove</button>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script lang="ts">
export default {
  props: {
    list: Array,
  },
};
</script>
