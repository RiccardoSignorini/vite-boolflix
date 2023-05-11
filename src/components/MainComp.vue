<script>
    import SingleCover from "./SingleCover.vue"
    import {store} from "../store"

    export default{
        name: "MainComp",
        components: {
            SingleCover,
        },
        data(){
            return{
                store
            }
        },
    }
</script>

<template>
  <div id="main">
    <div class="container">
        <div id="covers" class="container p-4">
            <div class="row justify-content-center">
                <h3 class="my-4">FILM</h3>
                <SingleCover v-for="(elem,index) in store.arrayMovie" :key="index" :coverDates="elem"/>
                <h3 class="my-4">SERIE TV</h3>
                <SingleCover v-for="(elem,index) in store.arrayTv" :key="index" :coverDates="elem"/>
            </div>
        </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
    #main{
        height: 90vh;
        overflow: scroll;
    }
</style>