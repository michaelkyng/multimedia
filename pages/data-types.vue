<template>
  <div class="min-h-screen max-w-[80%] mx-auto">
    <div class="flex flex-col min-h-screen justify-center gap-8">
      <p class="text-center text-3xl text-white/90 font-bold">Data Types</p>
      <div class="grid grid-cols-6 gap-5 h-96">
        <div class="left bg-[#0A131C] rounded-3xl">
          <div class="flex flex-col gap-5 h-full justify-center">
            <button
              :key="category.id"
              @click="tab = category.id"
              class="text-white/90 text-2xl text-center py-3"
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
        <div class="right col-span-5 bg-[#0A131C] rounded-3xl p-5">
          <div class="flex flex-col gap-14 h-full" v-if="tab === 0">
            <p class="text-white/90 text-xl font-medium mt-3">
              About this Project
            </p>
            <p
              class="grow bg-[#0C1721] rounded-3xl text-white/90 p-5 text-justify"
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
            <div class="grow">
              <img
                src="/images/frame1.png"
                class="rounded-3xl p-5 object-fill h-64 w-full"
              />
            </div>
          </div>

          <div class="flex flex-col gap-14 h-full" v-else-if="tab === 2">
            <p class="text-white/90 text-xl font-medium mt-3">Sample Audio</p>
            <div class="grow flex justify-center items-center">
              <audio controls>
                <source src="/audio/audio.mp3" type="audio/mp3" />
                Your browser does not support the audio element.
              </audio>
            </div>
          </div>

          <div class="flex flex-col gap-14 h-full" v-else-if="tab === 3">
            <p class="text-white/90 text-xl font-medium mt-3">Sample Video</p>
            <div class="grow">
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
import { equal } from "assert";

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
