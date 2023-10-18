<script setup lang="ts">
import { onMounted, ref } from "vue";
import Counter from "./components/Counter.vue";

const counters = [
  {
    text: "Twitter Followers",
    target: 12000,
    icon: "/twitter.svg",
    alt: "twitter icon",
  },
  {
    text: "Facebook Followers",
    target: 75000,
    icon: "/facebook.svg",
    alt: "facebook icon",
  },
  {
    text: "Youtube Subscribers",
    target: 5000,
    icon: "/youtube.svg",
    alt: "youtube icon",
  },
];

const progress = ref(0);

onMounted(() => {
  const timer = setInterval(() => {
    if (progress.value >= 1) return clearInterval(timer);

    progress.value += 0.005;
  }, 5);
});
</script>

<template>
  <main class="hero is-fullheight is-light">
    <div class="hero-body">
      <div class="level" style="margin: 0 auto">
        <Counter
          v-for="counter in counters"
          :text="counter.text"
          :target="counter.target"
          :icon="counter.icon"
          :alt="counter.alt"
          :current="progress"
          class="level-item"
          style="padding: 1rem 2rem"
        />
      </div>
    </div>
  </main>
</template>
