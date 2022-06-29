<script setup>
import headers from '../components/header.vue'
import footers from '../components/footer.vue'

import bodys from '../components/bodyComp/addForm.vue'
 
</script>
<template>
  <div class="flex min-h-screen"> 
   
    <div class="flex-1"> 
     <headers /> 

      <bodys />

    </div>
  </div>
  <footers />

</template>