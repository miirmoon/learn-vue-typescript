<template>
  <div>
    <label for="todo-input">오늘 할 일: </label>
    <input id="todo-input" type="text" :value="item" @input="handleInput" />
    <button @click="addTodo" type="button">add</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    item: {
      type: String,
      required: true,
    },
  },

  methods: {
    handleInput(event: InputEvent) {
      const eventTarget = event.target as HTMLInputElement;
      this.$emit("inputVal", eventTarget.value);
    },
    addTodo() {
      this.$emit("add");
    },
  },

  // setup(props, { emit }) {
  //   const handleInput = (event: InputEvent) => {
  //     const eventTarget = event.target as HTMLInputElement;
  //     emit("inputVal", eventTarget.value);
  //   };
  //   const addTodo = () => {
  //     emit("add");
  //   };
  //   return {
  //     handleInput,
  //     addTodo,
  //   };
  // },
});
</script>

<style scoped></style>
