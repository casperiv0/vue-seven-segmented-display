<script setup lang="ts">
import { ref } from "vue";
import SegmentItem from "./SegmentItem.vue";
const SEGMENT_IDS = ref(["a", "f", "g", "b", "e", "g", "c", "d"]);

const LETTERS_ENABLED_SEGMENTS = {
  0: ["a", "b", "c", "d", "e", "f"],
  1: ["b", "c"],
  2: ["a", "b", "g", "e", "d"],
  3: ["a", "b", "c", "d", "g"],
  4: ["b", "c", "g", "f"],
  5: ["a", "c", "d", "f", "g"],
  6: ["a", "c", "d", "e", "f", "g"],
  7: ["a", "b", "c"],
  8: ["a", "b", "c", "d", "e", "f", "g"],
  9: ["a", "b", "c", "d", "f", "g"],
  A: ["a", "b", "c", "e", "f", "g"],
  b: ["c", "d", "e", "f", "g"],
  C: ["a", "d", "e", "f"],
  d: ["b", "c", "d", "e", "g"],
  E: ["a", "d", "e", "f", "g"],
  F: ["a", "e", "f", "g"],
  _: ["d"],
  "-": ["g"],
};
</script>

<template>
  <div :key="index" v-for="(enabledSegments, index) in LETTERS_ENABLED_SEGMENTS">
    <div class="segment-container">
      <SegmentItem
        v-for="segment of SEGMENT_IDS"
        :enabledSegments="enabledSegments"
        :key="segment"
        :segment="segment"
      />
    </div>
  </div>
</template>

<style scoped>
.segment-container {
  border-radius: 1em;
  padding: 2em;
  background: #000;
  display: grid;
  gap: 0.2em;
  align-items: center;
  justify-content: center;

  grid-template-areas:
    "f a b"
    "f g b"
    "e g c"
    "e d c";
}
</style>
