<script>
  import HeaderComp from "./components/HeaderComp.vue"
  import MainComp from "./components/MainComp.vue"
  import axios from "axios"
  import {store} from "./store"

  export default{
    name: "App",
    components: {
      HeaderComp,
      MainComp
    },
    data(){
      return{
        store
      }
    },
    created(){
      this.apiMovieSearch()
    },
    methods: {
      // CHIAMATA API MOVIE
      apiMovieSearch(){
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=70766b0348a90acc7e1c8784e2eea324&query=${store.inputSearch}`).then((res)=>{
          console.log(res.data.results)
          store.arrayMovie = res.data.results
        })  
      }
    }
  }
</script>

<template>
  <HeaderComp @startSearch="apiMovieSearch()"/>
  <MainComp/>
</template>

<style lang="scss">

</style>