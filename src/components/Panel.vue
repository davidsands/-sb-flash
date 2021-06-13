<template>
  <div class="panel">
  <button class="option" v-for="opt in options" @click="opt.cb">
    {{opt.text}}
  </button>
  </div>
</template>
<script>
export default {
  name: 'Panel',
  data: function() { 
    return {
  }},
  props: {
    options: [Object],
  },
  computed: {
    card: function() { return this.cards[this.idx]; },
  }
}
</script>
<style>
  .panel {
    width: 100vw;
    background: #eee8;
    padding: 5px;
    display: flex;
    flex-direction: horizontal;
    justify-content: center;
    align-items: center;
    position: absolute;
    bottom: 5px;
  }
  .option {
    width: 5em;
    margin: 2px;
  }
</style>