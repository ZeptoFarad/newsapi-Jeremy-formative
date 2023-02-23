<script setup>
// import here
import navComponent from "./components/navcomponent.vue";
import searchAndAccept from "./components/searchAndAccept.vue";
// import buttonSuggestions from "./components/blockButtons.vue"
import displayArticle from "./components/myArticles.vue"

</script>

<template>
   <nav>
      <navComponent /> 
      <div class="searchBar">
        <h3>Search:</h3>
        <input type="text" placeholder="Put Search In Here" v-model="search_query">
        </div>
<div class="button_wrapper">
  
    <button @click="getNewsAritcles()" >Accept</button>
 
  </div>

    </nav>
    
  <main>
   <div>
    <searchAndAccept class="displayNone"/>
    <buttonSuggestions class="displayNone"/>
    <displayArticle v-for="article in theNews" :articleProp="article"/>
    

    <div class="blue_bar"></div>
    
  </div>
  <div class="circle"></div>
  </main>
</template>

<script>
export default {
  data(){
    return{ //data variables start
      buttonSuggestions : ['Hacktavist','Technology', 'Pollution','Political', 'Today', 'Protests'],
      theNews: [],
      search_query:''
    } //data variables end
  }
  ,
  methods:{
     async getNewsAritcles(){
      const resp = await fetch('https://newsapi.org/v2/top-headlines?q='+this.search_query+'&from=2023-01-23&sortBy=publishedAt&apiKey=5b0f374897634f93bde27ae8325c18ae')
      const data = await resp.json()
      console.log(data)
      this.theNews = data.articles;
    }
  },
  created(){
    // this.getNewsAritcles();
    
  }
}
  

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
    padding: 40px 0px 15px 10px;
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




body{
  position: relative;
}
.blue_bar{
  background-color: #32297A;
  width: 10vh;
  height: 90vh;
  position: fixed;
  right:0;
  bottom: 0;
  z-index: -2;
}
.circle{
  height: 70vh;
  aspect-ratio: 1/1;
  position: fixed;
  background-color: #ECC755;
  border-radius: 1000px;
  left: -35vh;
  bottom: -35%;
 z-index: -1;
}
.displayNone{
  display: none;
}

</style>
