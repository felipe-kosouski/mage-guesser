<template>
  <v-container fluid>
    <div v-if="showText">
      <v-flex>
      <h2>Eu sou um mago adivinhador, aposto que consigo adivinhar em qual número você está pensando...</h2>
      <h2>Me de apenas algumas tentativas, ainda estou aprendendo</h2>
      <h2>Primeiro, pense em um número entre 0 e 1000, e assim que tiver pensado, aperte em jogar</h2>
      <h2>Mas não vale mudar de número viu?</h2>
      <v-btn color="success" @click="gameStart()">Jogar</v-btn>
      </v-flex>
    </div>

    <div v-if="gameActive">
      <v-row>
        <v-col cols="12">
          <h2>Por acaso seu número é {{guess}}?</h2>
        </v-col>
      </v-row>
      
      <v-row justify="center">
        <v-col cols="1">
          <v-btn color="primary" @click="guessHigher()">É maior</v-btn>
        </v-col>

        <v-col cols="1">
          <v-btn color="primary" @click="guessLower()">É menor</v-btn>
        </v-col>
      </v-row>

      <v-flex>
        <v-btn color="success" @click="guessCorrect()">Acerto Miseravi</v-btn>
      </v-flex>

      <div v-if="gameWin">
        <v-row justify="center">
          <v-col cols="5">
            <h2>{{winText}}</h2>
          <v-btn color="success" @click="gameStart()">Jogar novamente</v-btn>
          </v-col>
        </v-row>
      </div>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      gameWin: false,
      winText: "Uhul, falei que eu iria conseguir",
      showText: true,
      gameActive: false,
      name: "",
      lowerNum: 0,
      higherNum: 1000,
      guess: 0
    }
  },
  methods: {
    gameStart() {
      this.gameWin = false
      this.lowerNum = 0
      this.higherNum = 1000
      this.showText = false
      this.gameActive = true
      this.guess = Math.floor((this.lowerNum+this.higherNum)/2)
    },
    guessHigher() {
      this.lowerNum = this.guess+1
      this.guess = Math.floor((this.lowerNum+this.higherNum)/2)
    },
    guessLower() {
      this.higherNum = this.guess-1
      this.guess = Math.floor((this.lowerNum+this.higherNum)/2)
    },
    guessCorrect() {
      this.gameWin = true
    }
  }
}
</script>

<style>
  .img-round{
    border-radius: 500em;
  }
</style>