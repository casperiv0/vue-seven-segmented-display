<script setup lang="ts">
const props = defineProps(["segment", "disabledIds"]);

const visibility = (id: string) => {
  return props.disabledIds.includes(id) ? "hidden" : "visible";
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

  background-color: #ff0000;
  color: black;
}
</style>
