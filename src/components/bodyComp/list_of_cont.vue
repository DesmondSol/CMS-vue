<script setup>
import { useQuery, useResult } from '@vue/apollo-composable'
import gql from 'graphql-tag'


    const { result, loading, error, refetch } = useQuery(gql`
  #     query countries {
  #     countries{
  # 	emoji
  #   name
  #   continent{
  #     name 
  #   }
  #   code
  #   phone
  #   capital
  #   currency
  #   languages{
  #     name
  #   }
  #   states{
  #     name
  #   }
  # }
  #   }

  query getAllPages {
  getAllPages{
    id
    title
    description
    image_url
  }
}
    `)

   // const countries = useResult(result)
const getAllPages = useResult(result)


</script>

<template>
 <div class="grid grid-cols-4 gap-4">
  <div v-if="loading">Loading...</div>

  <div v-else-if="error">Error: {{ error.message }}</div>

<!-- problwm here check-->
<a href="#"  v-for="page of getAllPages" :key="page.id" @click="$router.push('/viewedit')" class="block p-6 space-x-4 place-content_center bg-white rounded-lg border border-gray-200 shadow-md hover:bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700">
    <div class="flex place-content-center"><img :src="page.image_url " alt="img"></div>
    <div class="">
    <h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white"> 
       {{ page.title }}</h5>
    <div class=" font-normal text-gray-700 dark:text-gray-400 flex space-x-4">
     <div> Discription: {{page.description.slice(0,160)}}...  </div>
  
    </div>
    </div>
    
</a>
</div>

<div class="flex content-center justify-center">
<button @click="$router.push('/addPage')" type="button" class=" my-2  text-gray-900 bg-white border border-gray-300 focus:outline-none hover:bg-gray-100 focus:ring-4 focus:ring-gray-200 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 dark:bg-gray-800 dark:text-white dark:border-gray-600 dark:hover:bg-gray-700 dark:hover:border-gray-600 dark:focus:ring-gray-700">
+ Add Page
</button></div>
</template>


<style>

img {
  border-radius: 50%;
  width: 190px;
  height: auto;
}
 

  div {
    display: inline;
  }
</style>
//https://v4.apollo.vuejs.org/guide-composable/query.html#refetching