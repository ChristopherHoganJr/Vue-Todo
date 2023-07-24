<script setup></script>

<template>
  <button class="px-2 py-4 border border-black">
    <!-- slot with nothing in it will require props from parent call -->
    <!-- <slot></slot> -->
    <!-- can also create fallback content if nothing is given -->
    <slot>Create Todo</slot>
    <!-- can add names to each slot by adding #name -->
    <!-- <slot name="icon"></slot> -->
  </button>
</template>
