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
    <div id="header" class="d-flex justify-content-between container align-items-center">
        <div>
            <h2>BOOLFLIX</h2>
        </div>
        <div>
            <input type="text" placeholder="Cerca film o serie TV..." v-model="store.inputSearch" @keyup="$emit('startSearch')">
            <button class="m-3" @click="$emit('startSearch')">
                <i class="fa-solid fa-magnifying-glass"></i>
            </button>
        </div>    
    </div>
</template>

<style scoped lang="scss">
    #header{
        height: 10vh;

        h2{
            color: red;
        }
        
        button, input{
            border: 1px solid white;
            padding: 10px;
            border-radius: 15px;
        }    
    }
</style>