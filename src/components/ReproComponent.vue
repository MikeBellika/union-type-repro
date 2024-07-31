<script setup lang="ts">
import { computed } from "vue";

const props = defineProps<
  | { text: string; subheading: { text: string } }
  | { text?: undefined; subheading?: undefined }
>();
const testInScript = computed(() => {
  if (props.text) {
    // This works
    return props.subheading.text;
  }
  return "default value";
});
</script>
<template>
  <div v-if="text">
    <h1>{{ text }}</h1>
    <!-- This doesn't work -->
    {{ subheading.text }}
    <!-- '__VLS_ctx.subheading' is possibly 'undefined'. -->
  </div>
  <div v-else>{{ testInScript }}</div>
</template>
