<script setup lang="ts">
defineProps<{
  target: number;
  current: number;
  text: string;
  icon: string;
  alt: string;
}>();
</script>

<template>
  <div style="text-align: center; flex-direction: column">
    <img
      class="image is-48x48"
      :src="icon"
      :alt="alt"
      style="margin-bottom: 0.65rem"
    />
    <p class="heading">{{ text }}</p>
    <p class="title">{{ Math.floor(target * current) }}</p>
  </div>
</template>
