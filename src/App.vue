<script setup lang="ts">
import SegmentsContainer from "@/components/SegmentsContainer.vue";
import { store } from "@/store";
import SliderComponent from "@/components/SliderComponent.vue";
</script>

<template>
  <main>
    <SliderComponent />

    <div :style="{ fontSize: `${store.size / 100}em` }" class="container">
      <SegmentsContainer />
    </div>
  </main>
</template>

<style scoped>
main {
  margin: 0 auto;
  max-width: 1300px;
}

.container {
  display: flex;
  flex-wrap: wrap;
  gap: 3em;
}
</style>
