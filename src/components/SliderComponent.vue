<script setup lang="ts">
import { store } from "@/store";
</script>

<template>
  <div class="container">
    <div class="slider-container">
      <label for="font_size">Font Size</label>
      <input id="font_size" min="10" maxlength="100" type="range" v-model="store.size" />
    </div>

    <div class="checkbox-container">
      <input id="show_segment_ids" type="checkbox" v-model="store.showSegmentIds" />
      <label for="show_segment_ids">Show segment ids</label>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  gap: 2em;
  margin-bottom: 3em;
}

.slider-container {
  display: flex;
  flex-direction: column;
  max-width: fit-content;
}

.checkbox-container {
  display: flex;
  align-items: center;
  gap: 0.5em;
}
</style>
