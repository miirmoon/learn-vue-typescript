<template>
  <li>
    <span>{{ todoItem }}</span>
    <button @click="removeItem">삭제</button>
  </li>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    todoItem: String,
    index: Number,
  },
  methods: {
    removeItem() {
      this.$emit("remove", this.index);
    },
  },
});
</script>

<style scoped></style>
