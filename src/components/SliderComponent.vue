<script setup lang="ts">
import { store } from "@/store";
</script>

<template>
  <div class="slider-container">
    <label for="font_size">Font Size</label>
    <input id="font_size" min="10" maxlength="100" type="range" v-model="store.size" />
  </div>
</template>

<style scoped>
.slider-container {
  margin-bottom: 3em;

  display: flex;
  flex-direction: column;
  max-width: fit-content;
}
</style>
