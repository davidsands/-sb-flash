<template>
  <div id="app">
    <Flash msg="欢迎来到你的新<br>Flash 应用" 
      :cards = "cards"
     />
  </div>
</template>

<script>
import Flash from './components/Flash.vue'
import cards from './cards.js';

export default {
  name: 'App',
  components: {
    Flash
  },
  data : function() {
    return {
    cards: cards
  }}
}
</script>

<style>
#logo {
  width: 25vw;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
