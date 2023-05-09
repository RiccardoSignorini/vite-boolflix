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
      this.callApi()
    },
    methods: {
      // CHIAMATA API MOVIE
      callApi(){
        axios.get("https://api.themoviedb.org/3/movie/550?api_key=70766b0348a90acc7e1c8784e2eea324").then((res)=>{
          console.log(res.data)
          this.store.arrayMovie = res.data.data
        })  
      }
    }
  }
</script>

<template>
  <HeaderComp/>
  <MainComp/>
</template>

<style lang="scss">

</style>
