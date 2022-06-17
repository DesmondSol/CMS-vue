<script setup>
import { useQuery, useResult } from '@vue/apollo-composable'
import gql from 'graphql-tag'
//msg

    const { result, loading, error, refetch } = useQuery(gql`
  query getPage{
   getPage(id:1){ 
    id
    description
    title
    image_url
    
  }
}
`)

   // const countries = useResult(result)
const getPage = useResult(result)


</script>

<template>
 <div class="flex justify-center content-center">
  <div v-if="loading">Loading...</div>

  <div v-else-if="error">Error: {{ error.message }}</div>

<h1>{{getPage}}</h1>
    
    

</div>


</template>


<style>

img {
  border-radius: 50%;
  width: 500px;
  height: auto;
}
 

  div {
    display: inline;
  }
</style>
//https://v4.apollo.vuejs.org/guide-composable/query.html#refetching