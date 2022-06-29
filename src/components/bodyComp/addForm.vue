<script setup>
import { useMutation } from '@vue/apollo-composable'
import gql from 'graphql-tag'






</script>
<template>
  <div class="flex justify-center items-center mt-52">
    <div class="w-full max-w-xs">
      <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
        <div class="entry-input-title mb-4">
          <label
            for="entry"
            class="block text-gray-700 text-sm font-bold mb-2"
          >
            Title</label
          >
          <input
            id="title"
            class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
            type="text"
            placeholder="Title"
            aria-describedby="titleHelp"
            v-model="title"
          />
          <span class="text-xs text-red-700" id="titleHelp"></span>
        </div>

        <div class="entry-input-desc mb-6">
          <label
            for="entry"
            class="block text-gray-700 text-sm font-bold mb-2"
            >Description</label
          >

          <input
            aria-describedby="descHelp"
            v-model="desc"

            class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
            id="descriptions"
            type="text"
            placeholder="description"
          />

          <span class="text-xs text-red-700" id="descHelp"></span>
        </div>
<div class="entry-input-img mb-6">
          <label
            for="entry"
            class="block text-gray-700 text-sm font-bold mb-2"
            >Image</label
          >

          <input
            aria-describedby="imgHelp"
            v-model="img"

            class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
            id="descriptions"
            type="text"
            placeholder="images"
          />

          <span class="text-xs text-red-700" id="imgHelp"></span>
        </div>

        <div class="flex items-center justify-between">
          <button
            class="bg-blue-600 hover:bg-black text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
            type="submit"
          >
            AddPage
          </button>
          <a
          @click="$router.push('/')"
            class="inline-block align-baseline font-bold text-sm text-blue-500 hover:text-blue-800"
            href="#"
          >
            Back
          </a>
        </div>
      </form>
    </div>
  </div>
</template>