<template>
  <v-app>
    

    <v-content>
      <app-content></app-content>
    </v-content>

    <app-footer></app-footer>
  </v-app>
</template>

<script>
import Content from './components/layout/Content'
import Footer from './components/layout/Footer'

export default {
  name: 'App',
  data: () => ({
    //
  }),
  components: {
    'appFooter' : Footer,
    'appContent': Content
  }
};
</script>
