<template>
  <div>
    <h2>Vamos começar...</h2>
    <h2>Primeiro, me diga seu nome, assim eu consigo te conhecer melhor</h2>
    <h2>Agora, pense em um número de 0 a 1000</h2>
    <h2>Pensou?.... hmmmm seu número é {{guess}} </h2>
    <v-btn color="success" @click="guessHigher()">É maior</v-btn>
    <v-btn color="success" @click="guessLower()">É menor</v-btn>
    <v-btn color="success" @click="guessCorrect()">Acerto Miseravi</v-btn>
  </div>
  
</template>

<script>
export default {
  data() {
    return {
      name: "",
      lowerNum: 0,
      higherNum: 1000,
      guess: 0
    }
  },
  mounted: {
    guessGameStart() {
      //this.name = text
      this.guess = ((this.lowerNum+this.higherNum)/2)
    }
  },
  methods: {
    guessHigher() {
      this.lowerNum = this.guess+1
    },
    guessLower() {
      this.higherNum = this.guess-1
    },
    guessCorrect() {
      console.log("acerto");
      
    }
  }
}
</script>

<style>

</style>