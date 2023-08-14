<template>
  <div
    class="h-screen flex grow justify-center max-w-full sm:max-w-[90%] lg:max-w-[80%] mx-auto"
  >
    <div
      class="flex flex-col justify-center gap-8 overflow-auto h-auto py-40 w-full"
    >
      <p class="text-center text-3xl text-white/90 font-bold grow-0">
        Data Types
      </p>
      <div class="grid grid-cols-6 gap-10 md:gap-5 h-96 grow">
        <div class="left col-span-6 md:col-span-1 bg-[#0A131C] rounded-3xl">
          <div class="flex flex-col gap-5 h-full justify-center">
            <button
              :key="category.id"
              @click="tab = category.id"
              class="text-white/90 text-lg md:text-2xl text-center py-3"
              :class="{
                'bg-[#101B26] font-medium border-r border-r-blue-500':
                  tab === category.id,
                'bg-none': tab !== category.id,
              }"
              v-for="category in categories"
            >
              {{ category.text }}
            </button>
          </div>
        </div>
        <div
          class="right col-span-6 md:col-span-5 bg-[#0A131C] rounded-3xl p-5"
        >
          <div class="flex flex-col gap-14 h-full" v-if="tab === 0">
            <p class="text-white/90 text-xl font-medium mt-3">
              About this Project
            </p>
            <p
              class="grow bg-[#0C1721] rounded-3xl text-white/90 p-5 text-justify h-96 overflow-auto"
            >
              The text data type is a versatile and commonly used data type in
              various programming languages and databases for storing textual or
              string-based data. Unlike other data types like integers, floats,
              or boolean that store numerical or binary data, a text data type
              is designed to store a sequence of characters or alphabets that
              collectively form words, sentences, or even entire documents. In
              databases like SQL, a text data type can hold a string with a
              maximum length of 2^31-1 characters, which makes it a suitable
              choice for storing large amounts of textual data, like blog posts
              or articles. Regardless of the programming language or database
              system in use, understanding and properly using the text data type
              is crucial for handling and manipulating string data effectively.
            </p>
          </div>

          <div class="flex flex-col gap-14 h-full" v-else-if="tab === 1">
            <p class="text-white/90 text-xl font-medium mt-3">Sample Image</p>
            <div class="h-96 w-5/6 mx-auto flex justify-center items-center">
              <img
                src="/images/frame1.png"
                class="rounded-3xl p-5 object-fit h-64 w-full grow"
              />
            </div>
          </div>

          <div class="flex flex-col gap-14 h-full" v-else-if="tab === 2">
            <p class="text-white/90 text-xl font-medium mt-3">Sample Audio</p>
            <div class="grow h-96 flex justify-center items-center">
              <audio class="w-4/6" controls>
                <source src="/audio/audio.mp3" type="audio/mp3" />
                Your browser does not support the audio element.
              </audio>
            </div>
          </div>

          <div class="flex flex-col gap-14 h-full" v-else-if="tab === 3">
            <p class="text-white/90 text-xl font-medium mt-3">Sample Video</p>
            <div class="grow h-96 flex justify-center items-center">
              <video class="h-64 w-full" controls>
                <source src="/video/video.mp4" type="video/mp4" />
                Your browser does not support the audio element.
              </video>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: "data",
});

const tab = ref(0);
const categories = [
  { id: 0, text: "Text" },
  { id: 1, text: "Image" },
  { id: 2, text: "Audio" },
  { id: 3, text: "Video" },
];
</script>

<style scoped></style>
