<template>
  <!-- HTML -->
  <main>
    <div class="burger_menu"><img src="../assets/burger_menu.svg" alt="" srcset=""></div>
    <div class="nav_options">
      <h2>Home</h2>
      <h2>About</h2>
    </div>
    <div class="right_side">
    <div class="logo_words">
      <h1>NewsAPI</h1>
    </div>
    <div class="logo_box">
      <img src="../assets/eye.svg" alt="" />
    </div>
  </div>
  </main>
</template>

<script></script>

<style scoped>
@font-face {
  font-family: 'Coolvetica';
  src: url(../assets/coolvetica.ttf);
  
}
main {
  position: fixed;
  top: 0;
  width: 100vw;
  display: flex;
  background-color: #ecc755;
align-items: center;
justify-content: space-between;
height: 10vh;
z-index: 99;

}
.right_side{
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.logo_box{
  display: flex;
  background-color: #5D4051;
  aspect-ratio: 1/1;
  width: 10vh;
  align-items: center;
  justify-content: center;
}
.burger_menu{
  margin-left: 15px;
}
.nav_options {
  display: none;
}
.logo_words{
  font-family: 'Coolvetica';
  font-size: clamp(30px,0.5vh, 84px);
  
}  
.logo_words h1{
  margin: 0 20px 0 0;
  font-weight: 100;
}

</style>
