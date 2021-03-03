<template>
  <div class="ne-sorayim">
    <h1>Ne öğreneyim?</h1>
    <p>🤔</p>
    <div 
      class="soruyorum"
      v-bind:class="{ 'soruyorum-animated': animateSoruyorum }"
      v-on:animationend="onSoruyorumAnimationEnd()"
    >
      <span class="omu-sumu">{{ bunuMu[bunuMuIdx] }}</span>
      öğreneyim yoksa
      <span class="omu-sumu">{{ sunuMu[sunuMuIdx] }}</span>
      öğreneyim?
    </div>
    <div class="generate-btn" v-on:click="random">
      Generate
    </div>
  </div>
</template>

<script>
export default {
  name: 'Core',
  created() {
    this.random();
  },

  data: () => ({
    bunuMuIdx: 0,
    sunuMuIdx: 0,
    animateSoruyorum: true,

    bunuMu: [
      'Karbüratör mü',
      'Rocket launcher mı',
      'Patates kızartması mı',
      'Lahana sarması mı',
      'Beyin cerrahisi mi',
      'ErikThePlum mı',
      'Vites topuzu mu',
      'Pancar motoru mu',
      'Kereste mi',
      'Salatalık turşusu mu',
      'İçten yanmalı motor mu',
      'Yamaç paraşütü mü',
      'Bitcoin mi',
      'Bilgisayar kullanmayı mı',
      'Bahçe hortumu mu',
      'Demir testeresi mi',
      'İp atlamayı mı',
      'Kamyon amortisörü mü',
      'Brainfuck mı',
      'CuntScript mi',
      'Cunt Empire mı',
      'Pezevenklerin elinden kurtarma mı'
    ],

    sunuMu: [
      'PHP mi',
      'Laravel mi',
      'JavaScript mi',
      'Flutter mı',
      'iOS mi',
      'Java mı',
      'Elm mi',
      'Erlang mi',
      'TypeScript mi',
      'Dart mı'
    ]
  }),

  methods: {
    random() {
      this.bunuMuIdx = Math.floor(Math.random() * this.bunuMu.length);
      this.sunuMuIdx = Math.floor(Math.random() * this.sunuMu.length);
      this.animateSoruyorum = true
    },
    onSoruyorumAnimationEnd() {
      console.log('asgfdsg')
      this.animateSoruyorum = false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto&family=Roboto+Mono&display=swap');

.ne-sorayim {
  font-family: 'Roboto', sans-serif;
  text-align: center;
  font-size: 36px;
  padding: 30vh 1vh;
  color: #fff;
}
.omu-sumu {
  font-family: 'Roboto Mono', monospace;
  background-color: rgba(43, 47, 49);
  border-radius: 5px;
  padding: 2px 4px;
  margin: 0px 10px;
}
.generate-btn{
  cursor: pointer;
  margin-top: 3vh;
  font-size: 28px;
  display: inline-block;
  background-color: rgba(43, 47, 49);
  border-radius: 5px;
  padding: 2px 4px;
}
.generate-btn:hover {
  background-color: #999;
}
@keyframes bounce { 
   0% {transform: scale(0.3); opacity: 0;} 
   100% {transform: scale(1); opacity: 1;} 
}
.soruyorum-animated {
   animation-name: bounce; 
   animation-duration: 450ms;
   animation-timing-function: ease-in-out;
}
</style>
