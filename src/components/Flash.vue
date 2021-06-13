<template>
  <div>
    <h1 @click="show=!show" v-html="card.simp"/>
    <div v-if="show" class=pron>{{card.pron}}</div>
    <div v-if="show"class=defi>{{card.defi}}</div>
    <Panel :options="options"/>
  </div>
</template>

<script>
import Panel from './Panel.vue';
export default {
  name: 'Flash',
  components: {
    Panel,
  },
  data: function() { 
    return {
    idx: 0,
    options: [
      {text:"Prev",cb: this.prev},
      {text:"Weak",cb:function(){console.log('next');}},
      {text:"Fine",cb:function(){console.log('next');}},
      {text:"Next",cb: this.next},
    ],
    show: false,
  }},
  props: {
    msg: String,
    cards: [Object],
  },
  computed: {
    card: function() { return this.cards[this.idx]; },
  },
  methods: {
    incIdx: function(n) {
      if ( (this.idx + n) >= this.cards.length) {this.idx = 0; return;} 
      if ( (this.idx + n) < 0) {this.idx = this.cards.length - 1; return;}
      this.idx += n; 
    },
    next: function() {this.incIdx(1)},
    prev: function() {this.incIdx(-1)},
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  margin-bottom: 10px;
  font-weight: normal;
  color: #228f;
  line-height: 1.2;
}
.pron {
  color: #622c;
  margin-bottom: 10px;
}
.defi {
  color: 282c;
}
</style>
