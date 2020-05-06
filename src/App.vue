<template>
  <div id="app">
    <Menu />    
    <hr>
    
    <div class="container" id="componente">
      <div class="row center-align">
        <Game />  
        <hr>  
      </div>
    </div>

  </div>  
</template>

<script>
  import Menu from './components/Menu';
  import Game from './components/Game';

  export default {
    name: 'App',
    
    components: {
      Menu,
      Game,
    }
  }

</script>

<style>
body{
  background-color: #836FFF;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#componente{
  text-align: center;
}

</style>
