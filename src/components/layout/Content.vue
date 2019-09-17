<template>
  <v-container>
    <v-layout text-center wrap>
      <v-flex md12>
        <v-img class="img-round" :src=imgLink contain height="300"></v-img>
      </v-flex>

      <v-flex>
        <router-view></router-view>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      imgLink: "https://i.kinja-img.com/gawker-media/image/upload/s--XiNBYrPr--/c_scale,f_auto,fl_progressive,q_80,w_800/yrqzizwiknihxhbrmfsy.png"
    }
  },
}
</script>

<style>

</style>