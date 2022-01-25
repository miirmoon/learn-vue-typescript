<template>
  <li>{{ todoItem }}</li>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    todoItem: String,
  },
});
</script>

<style scoped></style>
