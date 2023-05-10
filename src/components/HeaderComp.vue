<script>
    import {store} from "../store.js"

    export default{
        name: "HeaderComp",
        data(){
            return{
                store
            }
        }
    }
</script>

<template>
    <div class="d-flex justify-content-between container">
        <div>
            <h2>BOOLFLIX</h2>
        </div>
        <div>
            <input type="text" placeholder="Cerca film o serie TV..." v-model="store.inputSearch">
            <button class="m-3" @click="$emit('startSearch')">Search</button>
        </div>    
    </div>
    
</template>

<style scoped lang="scss">
    button, input{
        border: 0;
    }
</style>