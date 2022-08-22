<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps(["segment", "disabledIds"]);

const visibility = (id: string) => {
  return props.disabledIds.includes(id) ? "hidden" : "visible";
};

const styles = {
  a: { width: "300px", height: "50px", visibility: visibility("a") },
  b: { width: "50px", height: "180px", visibility: visibility("b") },
  c: { width: "50px", height: "180px", visibility: visibility("c") },
  d: { width: "300px", height: "50px", visibility: visibility("d") },
  e: { width: "50px", height: "180px", visibility: visibility("e") },
  f: { width: "50px", height: "180px", visibility: visibility("f") },
  g: { width: "190px", height: "50px", visibility: visibility("g") },
} as Record<string, { width: string; height: string; visibility: "hidden" | "visible" }>;
const style = styles[props.segment];
</script>

<template>
  <p
    :style="{
      gridArea: segment,
      width: style.width,
      height: style.height,
      visibility: style.visibility,
    }"
    class="segment-item"
  >
    {{ segment }}
  </p>
</template>

<style scoped>
.segment-item {
  display: flex;
  align-items: center;
  justify-content: center;

  background-color: hsla(160, 100%, 37%, 1);
}
</style>
