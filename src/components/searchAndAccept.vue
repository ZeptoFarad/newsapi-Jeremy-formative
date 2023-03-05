<template>
<!-- HTML -->
 <main>
<div class="searchBar">
<h3>Component Search:</h3>
<input type="text">
</div>
<div class="button_wrapper">
    <button>Accept</button>
</div>

 </main>
</template>
<script>
</script>

<style scoped>
.button_wrapper{
    display: flex;
    justify-content: flex-end;
    
}

button{
    color: black;
    background-color:#ECC755;
    mix-blend-mode: difference;
    width: calc(10vh + 6rem);
    font-family: 'Coolvetica';
    font-size: 1.1rem;
    margin-top: 1rem;
    padding: 5px 10vh 5px 0;
    color:rgb(226, 16, 16);
    
}
.searchBar{
    display: flex;
    padding: 10px 15px;
    background-color: #F5EAE6;
    width: calc(85vw - 8vh);
    margin-top: 2.5rem;
    align-items: center;
}

.searchBar  h3{
    font-size: clamp(20px, 0.5vh, 40px);
    font-weight: bold;
    margin: 0 15px 0 0 ;
}

.searchBar input{
    width: 80%;
    max-width: 160px;
    height: clamp(25px, 0.5vh, 40px);
    
}

</style>