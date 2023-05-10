<script>
    import SingleCover from "./SingleCover.vue"
    import {store} from "../store"

    export default{
        name: "MainComp",
        components: {
            SingleCover
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
                <SingleCover v-for="(elem,index) in store.arrayMovie" :key="index" :coverDates="elem"/>
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