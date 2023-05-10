<script>
    export default{
        name: "SingleCover",
        props: ["coverDates"],
        created(){
        }
    }
    
</script>

<template>
    <div class="card m-2 col-lg-3">
        <img :src="coverDates.poster_path" alt="" class="card-img-top">
        <div class="card-body text-center align-items-center">
            <h5 class="card-title">{{coverDates.title}}</h5>
            <p class="card-text">{{coverDates.release_date}}</p>
            <div class="scroll">
                <p class="card-text">({{coverDates.overview}})</p>    
            </div>
        </div>
    </div>    
</template>

<style scoped lang="scss">
    .card{
        height: 300px;
    }
</style>