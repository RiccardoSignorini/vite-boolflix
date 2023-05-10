<script>
    import SingleCover from "./SingleCover.vue"
    import SingleCoverTv from "./SingleCoverTv.vue"
    import {store} from "../store"

    export default{
        name: "MainComp",
        components: {
            SingleCover,
            SingleCoverTv
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
            <div class="row justify-content-center text-center">
                <h3>FILM</h3>
                <SingleCover v-for="(elem,index) in store.arrayMovie" :key="index" :coverDates="elem"/>
                <h3>SERIE TV</h3>
                <SingleCoverTv v-for="(elem,index) in store.arrayTv" :key="index" :coverDates="elem"/>
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