<script>
import { markRaw } from 'vue'

    export default{
        name: "SingleCover",
        props: ["coverDates"],
        methods: {
            // PER NAME/TITLE ORIGINALI
            originalTitleName(){
                if(this.coverDates.original_title){
                    return this.coverDates.original_title
                } else{
                    return this.coverDates.original_name
                }
            },

            // PER NAME/TITLE
            titleName(){
                if(this.coverDates.title){
                    return this.coverDates.title
                } else{
                    return this.coverDates.name
                }
            },

            // VOTO TRASFORMATO DA 1 A 5
            mark(){
                return Math.ceil(this.coverDates.vote_average/2)
            }
        }
    }
    
</script>

<template>
    <div class="card m-4 col-lg-3">
        <img :src="`https://image.tmdb.org/t/p/w500{{coverDates.poster_path}}`" :alt="originalTitleName()" class="card-img-top">
        <div class="card-body text-center align-items-center">
            <h5 class="card-title">{{titleName()}}</h5>
            <p class="card-text">({{originalTitleName()}})</p>
            <p class="card-text">{{coverDates.release_date}}</p>
            <div class="scroll text-start">
                <p class="card-text">({{coverDates.overview}})</p>    
            </div>
            <span class="card-text">Mark: {{mark()}}</span>
            <span class="card-text">Lenguage: {{coverDates.original_language}}</span>
        </div>
    </div>    
</template>

<style scoped lang="scss">
    .card{
        height: 350px;
        background-color: black;
        border: 1px solid white;
        .scroll{
            height: 120px;
            border: 1px solid red;
            overflow: scroll;
        }
        span{
            margin: 0 5px;
        }
    }
</style>