<template>
  <div class="cards-container">

    <Card v-for="pokemon in pokemons" 
          :title="pokemon.name"
          :description="pokemon.url"
          :key="pokemon.name"
    />


  </div>
</template>

<script>

import axios from 'axios'
import Card from '@/components/SendtrackCard'

 export default {
// new Vue({
  data () {
    return {
      pokemons: [],
    }
  },
  components : {
    Card
  },
  asyncData(params){ //asyncData() is processed on the server side while data() is processed on the client side
  //asyncData allows to pre-render data from an API in a server first and in the browser second
    return axios.get("https://pokeapi.co/api/v2/pokemon/?limit=50&offset=1")
      .then(response => {
        console.log(response.data.results)
        return {
          pokemons : response.data.results,
          
        }
      })
      .catch(err => console.log("error while getting data from the API ", err))
  }

// })

 }
</script>