<script setup>
import { useQuery, useResult } from '@vue/apollo-composable'
import gql from 'graphql-tag'


    const { result, loading, error, refetch } = useQuery(gql`
      query countries {
      countries{
  	emoji
    name
    continent{
      name 
    }
    code
    phone
    capital
    currency
    languages{
      name
    }
    states{
      name
    }
  }
    }
    `)

    const countries = useResult(result)



</script>

<template>

  <div v-if="loading">Loading...</div>

  <div v-else-if="error">Error: {{ error.message }}</div>


<a href="#" v-for="country of countries" :key="country.id" class="block p-6 max-w-5xl bg-white rounded-lg border border-gray-200 shadow-md hover:bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700">
    <h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">{{ country.emoji }}  {{ country.name }}</h5>
    <div class="font-normal text-gray-700 dark:text-gray-400 flex space-x-4">
     <div> Continent: {{country.continent.name}}  </div>
     <div> Code: {{country.code}}      </div>
     <div> phone: {{country.phone}}</div>
     <div> capital: {{country.capital}}</div>
     <div> currency: {{country.currency}}</div>
    </div>
    <div class="font-normal text-gray-700 dark:text-gray-400 flex space-x-4">
     languages: <div v-for="language of country.languages.slice(0,8)" :key="language.name" > {{language.name}}  </div>
    </div>
 <div  class="font-normal text-gray-700 dark:text-gray-400 flex space-x-4">
    states:  <div v-for="states of country.states.slice(0,8)" :key="states.name"> {{states.name}} </div>
    </div>
    
</a>



<!-- 
  <table>
    <thead>
      <th>Country Name</th>
      <th>Country Emoji</th>
      <th>Country Code</th>
      <th>Country Capital</th>
      <th>Country Languages</th>
      <th>Country States</th>
    </thead>

    <tbody>
       <tr v-for="country of countries" :key="country.id">
        <td>{{ country.name }}</td>
        <td>{{ country.emoji }}</td>
        <td>{{ country.code }}</td>
        <td>{{ country.capital }}</td>

        <td >
          <div v-for="language in country.languages" :key="language.name">
            {{ language.name }}
          </div>
          </td>
        <td>
          <div v-for="states in country.states" :key="states.name">
            {{ states.name }}
          </div>
        </td>
       </tr>
    </tbody>
  </table> -->

</template>


<style>
  table,thead, td, th {
    border: 1px solid black;
    /* border-collapse: collapse; */
  }

  th {
    padding: 10px;
    background-color: lightblue;
  }

  td {
    background-color: lightgray;
  }

  table {
    margin: 20px
  }

  div {
    display: inline;
  }
</style>
//https://v4.apollo.vuejs.org/guide-composable/query.html#refetching