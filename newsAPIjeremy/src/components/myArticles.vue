<script setup>// when a component is meant to receive data from its parent component
// we declare a prop system with the code below
defineProps({
 articleProp: {
type: Object, // String, Number, Array, Object, Boolean
required: true
}
});
</script>

<template>
<!-- HTML -->
 <div class="wrapper">
    <div class="title">
        <h2>{{articleProp.title}}</h2>
    </div>
    <div class="content">
        <img :src="articleProp.urlToImage" v-if="articleProp.urlToImage">
        <p>{{ articleProp.content }}</p>

        
    </div>
    <form :action="articleProp.url">
    <button type="submit" >Read More >> </button>
</form>
 </div>
</template>

<style scoped>

img{
    background-color: lightcyan;
    object-fit: cover;
    width: 35vw;
    max-height: 60%;
    margin: 20px 0px 20px 20px;
    aspect-ratio: 1/1;
    float: right;
    border-radius: calc(200px - 30vw);
    shape-outside: circle();
}
p{
    text-align: justify;
    max-width: 60%;
    max-height: 80%;
    overflow: hidden;
    text-overflow: ellipsis;
}

.wrapper:nth-of-type(odd){
    position: relative;
    margin-top: 5rem;
    margin-left: 3rem;
    background-color: antiquewhite;
    
}
.wrapper:nth-of-type(even){
    position: relative;
    margin-top: 5rem;
    margin-right: 3rem;
    background-color: antiquewhite;
    
}

.wrapper:nth-of-type(odd) button{
    position: absolute;
    background-color:#32297A;
    padding: 4px 60px 4px 15px;
    right: 0;
    bottom: 20px;
    font-family: 'Roboto';
    color: aliceblue;
}
.wrapper:nth-of-type(even) button{
    position: absolute;
    background-color:#ECC755;
    padding: 4px 60px 4px 15px;
    left: 0;
    bottom: 20px;
    font-family: 'Roboto';
    color: black;
}
.content{
    overflow: hidden;
    height: 35vh;
    padding: 1rem;
    font-family: 'Ubuntu';
}
.title h2{
    font-size: clamp(16px, 6vw, 25px);
    font-family: 'Roboto';
    margin: 0.2rem 1.5rem;
    color: white;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
   -webkit-line-clamp: 1; /* number of lines to show */
    line-clamp: 1; 
   -webkit-box-orient: vertical;
}
.title:nth-of-type(odd){
position: absolute;
left: 0;
top: -20px;
background-color: #32297A;

}
.wrapper:nth-of-type(even) .title{
position: absolute;
margin-left: 3rem;
right: 0;
top: -20px;
background-color: #ECC755;
text-justify: right;
align-items: right;
}
.wrapper:first-of-type{
    margin-top: 8rem !important;
}



</style>