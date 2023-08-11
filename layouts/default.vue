<template>
  <div
    class="min-h-screen h-full flex flex-col bg-black bg-cover duration-300 transition-all ease-in"
    :style="{ 'background-image': `url('/images/frame${image_id}.png')` }"
  >
    <NavBar class="absolute min-w-full" />
    <div class="flex-1">
      <NuxtPage />
    </div>
  </div>
</template>

<script lang="ts" setup>
const max = 3;
const image_id = ref(1);

let intervalId: NodeJS.Timer | null = null;

onMounted(() => {
  intervalId = setInterval(() => {
    if (image_id.value >= 3) {
      image_id.value = 1;
    } else {
      image_id.value += 1;
    }
  }, 5 * 1000); // 15 * 1000 because setInterval expects milliseconds
});

onUnmounted(() => {
  if (!intervalId) return;
  clearInterval(intervalId); // it's a good practice to clear the interval when the component is unmounted to avoid memory leaks
});
</script>
