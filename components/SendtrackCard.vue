<template>
    <div class="card"> 
        <div class="card-text"> 
            <h1>{{title}} </h1>
            <p> {{description}}</p>
        </div>

    </div>
    
</template>

<script>
export default {
    props : ['title', 'description']    
}
</script>

<style scoped>

.card{
    box-sizing: border-box; 
    width : 40vw; 
    margin: 2vw;
    padding : 0; 
    border : 1px solid #ccc; 
    border-radius: 5px; 
    height : fit-content;
}

.card-text{
    padding : 1vw; 
}

.card-img{
    background-position : center; 
    background-size: 100%; 
    width : 100%; 
    height : 20vh; 
}

</style>