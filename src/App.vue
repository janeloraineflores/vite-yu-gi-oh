<script>
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue'
  import FooterComponent from './components/FooterComponent.vue'
  import axios from 'axios';

  export default {
    name: "App",
    components: {
      HeaderComponent,
      MainComponent,
      FooterComponent,
    },
    data() {
      return {
        cards: []
      };
    },
    methods: {},

    created() {
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then(response => {
          console.log(response.data.data);
          this.cards = response.data.data;
        
        })
    }
  };
</script>

<template>
  <HeaderComponent />

  <MainComponent :cards ="cards"/> 
  
  <FooterComponent />

</template>

<style lang="scss">
@use "assets/scss/main.scss"

</style>
