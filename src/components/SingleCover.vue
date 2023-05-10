<script>
    export default{
        name: "SingleCover",
        props: ["coverDates"],
        created(){
        }
    }
    
</script>

<template>
    <div class="card m-4 col-lg-3">
        <!-- <img src="https://image.tmdb.org/t/p/w300{{coverDates.backdrop_path}}" alt="" class="card-img-top"> -->
        <div class="card-body text-center align-items-center">
            <h5 class="card-title">{{coverDates.title}}</h5>
            <p class="card-text">({{coverDates.original_title}})</p>
            <p class="card-text">{{coverDates.release_date}}</p>
            <div class="scroll text-start">
                <p class="card-text">({{coverDates.overview}})</p>    
            </div>
            <span class="card-text">Mark: {{coverDates.vote_average}}</span>
            <span class="card-text">Lenguage: {{coverDates.original_language}}</span>
        </div>
    </div>    
</template>

<style scoped lang="scss">
    .card{
        height: 350px;
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