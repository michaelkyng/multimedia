<template>
  <nav>
    <div class="w-full flex items-center p-4 max-w-[80%] mx-auto">
      <NuxtLink to="/" class="text-white font-bold text-[1.5rem]"
        >MultiMedia</NuxtLink
      >

      <div class="flex justify-center w-full">
        <div
          class="flex justify-center bg-white/10 px-10 py-3.5 backdrop-blur-lg rounded-full gap-[2.5rem] mr-32"
        >
          <NuxtLink to="/" class="text-white/90 hover:text-white"
            >Home</NuxtLink
          >
          <NuxtLink to="/data-types" class="text-white/90 hover:text-white"
            >Data Type</NuxtLink
          >
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style scoped>
.router-link-active,
.router-link-exact-active {
  color: white;
}
</style>
