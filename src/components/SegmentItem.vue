<script setup lang="ts">
import { store } from "@/store";

const props = defineProps(["segment", "enabledSegments"]);

const visibility = (id: string) => {
  return props.enabledSegments.includes(id) ? "visible" : "hidden";
};

const styles = {
  a: { width: "12.5em", height: "2.5em", visibility: visibility("a") },
  b: { width: "2.5em", height: "11.25em", visibility: visibility("b") },
  c: { width: "2.5em", height: "11.25em", visibility: visibility("c") },
  d: { width: "12.5em", height: "2.5em", visibility: visibility("d") },
  e: { width: "2.5em", height: "11.25em", visibility: visibility("e") },
  f: { width: "2.5em", height: "11.25em", visibility: visibility("f") },
  g: { width: "100%", height: "2.5em", visibility: visibility("g") },
} as Record<string, { width: string; height: string; visibility: "hidden" | "visible" }>;
const style = styles[props.segment];
</script>

<template>
  <p :style="{ gridArea: segment, ...style }" class="segment-item">
    <span>{{ store.showSegmentIds ? segment : null }}</span>
  </p>
</template>

<style scoped>
.segment-item {
  display: flex;
  align-items: center;
  justify-content: center;

  background-color: #ff0000;
  color: black;
}

.segment-item span {
  font-size: 2em;
}
</style>
