<template>
  <div class="app">
    <Menu/>
    <div class="cover"></div>
    <div class="content">
      <router-view/>
    </div>
    <Footer/>
  </div>
</template>

<script>
  import Menu from './Menu';
  import Footer from './Footer';

  export default {
    components: {
      Menu,
      Footer,
    },
  };
</script>

<style>
html, body, .app{
  padding: 0;
  margin: 0;
  font-family: Arial;
  color: #123;
}
</style>

<style scoped>
.cover{
  width: 100%;
  height: 270px;
  background: url('./img/view.jpg') center center;
  background-size: cover;
}
.content{
  width: 100%;
  padding: 0 80px;
  box-sizing: border-box;
  min-height: calc(100vh - 371px);
}

@media(max-width: 450px){
  .content{
    padding: 0 40px;
  }
}
</style>
