<script setup lang="ts">
import ReproComponent from "./components/ReproComponent.vue";
</script>

<template>
  <h1>This is fine</h1>
  <ReproComponent :text="'hi'" :subheading="{ text: 'hi' }" />

  <h1>This should give an error</h1>
  <ReproComponent :text="'hi'" />

  <h1>This is also fine</h1>
  <ReproComponent />
</template>
