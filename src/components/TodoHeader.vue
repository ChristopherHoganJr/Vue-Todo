<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <header>
    <nav
      class="container mx-auto flex items-center justify-between bg-blue-200 py-5 px-2"
    >
      <div class="flex items-center w-full">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          strokeWidth="{1.5}"
          stroke="currentColor"
          class="w-12 h-12"
        >
          <path
            strokeLinecap="round"
            strokeLinejoin="round"
            d="M3.75 13.5l10.5-11.25L12 10.5h8.25L9.75 21.75 12 13.5H3.75z"
          />
        </svg>
        <h1 class="text-2xl font-bold">Vite + Vue Todos</h1>
      </div>
      <ul class="flex gap-3">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/testing">Testing</RouterLink>
      </ul>
    </nav>
  </header>
</template>
