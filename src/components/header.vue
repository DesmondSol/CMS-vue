<script >
import { ref } from 'vue'

// defineProps({
//   msg: String
// })
export default {
  setup() {
    const msg = ref('Hello Vue 3 + Vite')
    return {
      msg
    }
  },
  name: "blue-navbar",
  data() {
    return {
      showMenu: false
    }
  },
  methods: {
    toggleNavbar: function(){
      this.showMenu = !this.showMenu;
    }
  }
}

// const count = ref(0)
</script>


<template>

  
  <nav class="relative flex flex-wrap items-center justify-between px-2 py-3 mb-3 bg-zinc-500 ">
    <div class="container flex flex-wrap items-center justify-between px-4 mx-auto">
      <div class="relative flex justify-between w-full px-4 lg:w-auto lg:static lg:block lg:justify-start">
        <a class="inline-block py-2 mr-4 text-sm font-bold leading-relaxed text-white uppercase whitespace-nowrap" href="/">
          Demo Pages
        </a>
        <button class="block px-3 py-1 text-xl leading-none text-white bg-transparent border border-transparent border-solid rounded outline-none cursor-pointer lg:hidden focus:outline-none" type="button" v-on:click="toggleNavbar()">
          <i class="fas fa-bars"></i>
        </button>
      </div>
      <div v-bind:class="{'hidden': !showMenu, 'flex': showMenu}" class="items-center lg:flex lg:flex-grow">
        <ul class="flex flex-col ml-auto list-none lg:flex-row">
          <li class="nav-item">
            <a class="flex items-center px-3 py-2 text-xs font-bold leading-snug text-white uppercase hover:opacity-75" href="#">
              <i class="text-lg text-white opacity-75 fab fa-facebook-square leading-lg" /><span class="ml-2">Share</span>
            </a>
          </li>
          <li class="nav-item">
            <a class="flex items-center px-3 py-2 text-xs font-bold leading-snug text-white uppercase hover:opacity-75" href="#">
              <i class="text-lg text-white opacity-75 fab fa-twitter leading-lg" /><span class="ml-2">Tweet</span>
            </a>
          </li>
          <li class="nav-item">
            <a class="flex items-center px-3 py-2 text-xs font-bold leading-snug text-white uppercase hover:opacity-75" href="#">
              <i class="text-lg text-white opacity-75 fab fa-pinterest leading-lg" /><span class="ml-2">Pin</span>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>






 <!-- comment
  <h1>{{ msg }}</h1>


 <button type="button" @click="count++">count is: {{ count }}</button>
  <p>
    Edit
    <code>components/header.vue</code> to test hot module replacement.
  </p> -->
</template>

<style scoped>

</style>
