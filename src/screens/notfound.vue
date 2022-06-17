<script setup>
import headers from '../components/header.vue'
import footers from '../components/footer.vue'



</script>
  
<template>
  <div class="flex min-h-screen"> 
   
    <div class="flex-1"> 
     <headers /> 

   <div class="flex justify-center place-items-center">
    <a href="#" class="block p-6 max-w-sm bg-white rounded-lg border border-gray-200 shadow-md hover:bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700 content-center justify-center">
    <h5 class="flex mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white justify-center content-center">404</h5>
    <p class="flex font-normal text-gray-700 dark:text-gray-400 content-center justify-center">Page Not Found</p>
</a>
</div>

</div>
  </div>
  <footers />
</template>
