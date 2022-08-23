<script setup lang="ts">
import { ref } from "vue";
import SegmentItem from "./SegmentItem.vue";
const SEGMENT_IDS = ref(["a", "f", "g", "b", "e", "g", "c", "d"]);

const DISABLED_IDS = {
  0: ["g"],
  1: ["a", "f", "d", "e", "g"],
  2: ["c", "f"],
  3: ["e", "f"],
  4: ["a", "d", "e"],
  5: ["b", "e"],
  6: ["b"],
  7: ["d", "e", "f", "g"],
  8: [],
  9: ["e"],
  A: ["d"],
  b: ["a", "b"],
  C: ["b", "c", "g"],
  d: ["a", "f"],
  E: ["b", "c"],
  F: ["b", "c", "d"],
  _: ["a", "b", "c", "e", "f", "g"],
  "-": ["a", "b", "c", "e", "d", "f"],
};
</script>

<template>
  <div :key="index" v-for="(id, index) of DISABLED_IDS">
    <div class="segment-container">
      <SegmentItem
        :disabledIds="DISABLED_IDS[index]"
        :key="segment"
        v-for="segment of SEGMENT_IDS"
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
