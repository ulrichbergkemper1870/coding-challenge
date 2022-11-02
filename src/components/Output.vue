<template>
  <ul>
    <li v-for="(line, index) in lines" :key="index">{{ line }}</li>
  </ul>
</template>

<script type="ts">
import { defineComponent } from "vue";
export default defineComponent({
  props: {
    lines: [],
  },
});
</script>
