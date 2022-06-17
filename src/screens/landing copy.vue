<script setup>
import headers from '../components/header.vue'
import footers from '../components/footer.vue'
import sidebar from '../components/sidebar.vue'
import bodys from '../components/bodyComp/list_of_cont.vue'
 
</script>
<template>
    <div class="flex min-h-screen"> 
  <sidebar /> 

   <div class="flex-1"> 
     <headers /> 

      <bodys />

   </div>
</div>
  <footers />

</template>