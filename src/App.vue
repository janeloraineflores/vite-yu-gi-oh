<script>
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue'
  import FooterComponent from './components/FooterComponent.vue'
  import axios from 'axios';
  import { store } from './store.js';

  export default {
    name: "App",
    components: {
      HeaderComponent,
      MainComponent,
      FooterComponent,
    },
    data() {
      return {
        store,
        cards: [],
        archetypes: []
      };
    },

  methods : {
    getResults() { 
      axios
          .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype', {
            params: {
              archetype: this.store.searchArchetype
            }
          })
            
          .then(response => {
            this.cards = response.data.data
              console.log( response.data.data)
              
          })
    },
      
    performSearch(action = 'filter') {
        
        
        if(action == 'reset') {
          this.store.searchArchetype = '';
        }

        this.getResults();
  
    }     
  },

  created() {
  
      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then(response => {
        this.cards = response.data.data;
      })

      axios
        .get('https://db.ygoprodeck.com/api/v7/archetypes.php', {
        archetype_name: this.store.searchArchetype})
        
        
        .then(response => {
            this.archetypes = response.data
        })
  }
 
}      
     
</script>

<template>
  <HeaderComponent />

  <MainComponent :cards ="cards" :archetypes="archetypes" @search="performSearch()" /> 
  
  <FooterComponent />

</template>

<style lang="scss">
@use "assets/scss/main.scss"

</style>