<script setup>
import { reactive, ref, defineEmits } from "vue";
import TodoButton from "./TodoButton.vue";

// 2 ways of creating reactive data
// 1. Using the ref function
// const todo = ref("testing is updated");
// 2. Using the reactive function
const todoState = reactive({
  todo: "",
  invalid: null,
  errMsg: "",
});

// emit function is used to emit events to the parent component
const emit = defineEmits(["create-todo"]);
// create-todo is the name of the event that will be emitted to the parent component
const createTodo = () => {
  todoState.invalid = null;
  if (todoState.todo !== "") {
    emit("create-todo", todoState.todo);
    todoState.todo = "";
    return;
  }
  todoState.invalid = true;
  todoState.errMsg = "Todo value cannot be empty";
};
</script>

<template>
  <div
    :class="{ 'border-red-500': todoState.invalid }"
    class="flex transition-all border-2 border-slate-300 focus-within:shadow-lg w-full"
  >
    <input
      type="text"
      class="w-full py-1 px-2 focus:outline-none"
      v-model="todoState.todo"
    />
    <TodoButton @click="createTodo()" />
  </div>
  <!-- will only render to dom when v-if is true -->
  <!-- <p v-if="todoState.invalid" class="err-msg">{{ todoState.errMsg }}</p> -->
  <!-- will render to dom by default & switch display none  -->
  <p v-show="todoState.invalid" class="text-red-500 font-semibold my-1">
    {{ todoState.errMsg }}
  </p>
</template>

<style lang="scss" scoped></style>
