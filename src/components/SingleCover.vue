<script>
    import moment from "moment"

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
            },

            // INVERTIRE LA DATA
            invertDateFormat() {
                return moment(this.coverDates.release_date, 'YYYY/MM/DD').format('DD/MM/YYYY');
            }

            // PER RIMUOVERE GLI OVERVIEW CHE NON CI SONO
            // overview(){
            //     if(this.coverDates.overview !== ""){
            //         return this.coverDates.overview
            //     } else{

            //     }
            // }
        }
    }
    
</script>

<template>
    <div class="card m-4 col-lg-3">
        <img :src="`https://image.tmdb.org/t/p/w342{{coverDates.poster_path}}`" :alt="titleName()" class="card-img-top">
        <div class="card-body text-center align-items-center">
            <h5 class="card-title">{{titleName()}}</h5>
            <span class="card-text">({{originalTitleName()}})</span>
            <div>
                <i v-for="n in 5" :class=" (n<=mark()) ? 'fa-solid' : 'fa-regular' " class="fa-star"></i>
            </div>
            <p class="card-text">Release in {{invertDateFormat()}}</p>
            <div class="scroll text-start">
                <p class="card-text">({{coverDates.overview}})</p>    
            </div>
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
    }
</style>