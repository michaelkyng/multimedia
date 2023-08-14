<template>
  <nav class="bg-black/30 md:bg-black/0">
    <div
      class="grid grid-cols-3 justify-items-stretch items-center p-4 sm:max-w-full md:max-w-[90%] lg:max-w-[80%] mx-auto"
    >
      <div class="col-span-1">
        <NuxtLink
          to="/"
          class="text-white font-bold text-[1rem] md:text-[1.5rem] max-w-max"
          >MultiMedia</NuxtLink
        >
      </div>

      <div class="justify-self-center col-span-1">
        <div
          class="hidden justify-self-center md:justify-center bg-white/10 px-5 px-12 py-2 py-3.5 backdrop-blur-lg rounded-full gap-[2.5rem] sm:hidden md:flex"
        >
          <NuxtLink
            to="/"
            class="text-white/90 hover:text-white text-sm md:text-base"
            >Home</NuxtLink
          >
          <NuxtLink
            to="/data-types"
            class="text-white/90 hover:text-white text-sm md:text-base"
            >Data Type</NuxtLink
          >
        </div>
      </div>
      <div class="col-span-1 justify-self-end">
        <button class="md:hidden" @click="is_open = !is_open">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-6 h-6 text-white"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3.75 9h16.5m-16.5 6.75h16.5"
            />
          </svg>
        </button>
      </div>
    </div>
    <transition name="shutter" mode="in-out">
      <div v-if="is_open">
        <div
          class="flex w-full flex-col align-items-center px-5 px-10 py-2 py-3.5 gap-[2.5rem] md:hidden text-center"
        >
          <NuxtLink
            to="/"
            class="text-white/90 hover:text-white text-sm md:text-base"
            >Home</NuxtLink
          >
          <NuxtLink
            to="/data-types"
            class="text-white/90 hover:text-white text-sm md:text-base"
            >Data Type</NuxtLink
          >
        </div>
      </div>
    </transition>
  </nav>
</template>

<script lang-="ts" setup>
const is_open = ref(false);
</script>

<style scoped>
.router-link-active,
.router-link-exact-active {
  color: white;
}
.shutter-enter-active {
  animation: shutter-in-top 0.25s ease 0s 1 normal none;
}
.shutter-leave-active {
  animation: shutter-out-top 0.25s ease 0s 1 normal none;
}

@keyframes shutter-in-top {
  0% {
    transform: rotateX(-100deg);
    transform-origin: top;
    opacity: 0;
  }
  100% {
    transform: rotateX(0deg);
    transform-origin: top;
    opacity: 1;
  }
}
@keyframes shutter-out-top {
  0% {
    transform: rotateX(0deg);
    transform-origin: top;
    opacity: 1;
  }
  100% {
    transform: rotateX(70deg);
    transform-origin: top;
    opacity: 0;
  }
}
</style>
