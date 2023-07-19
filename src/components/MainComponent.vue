<script>
 import { store } from '../store.js';
    export default {
       
        name: "MainComponent",
        data() {
            return {
                store
            }
        },
        methods: {

        },

        props: {
            archetypes: {
                type: Array,
                default: []
            },

            cards :{
                type: Array, 
                default: []
            }
        }
    }
</script>

<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="col">
                    <form action= "" @submit.prevent="$emit('search', 'filter')"  >
                        <div class="row py-4">
                            <div class="col-2">
                                <select class="form-select" aria-label="Default select example" v-model="store.searchArchetype" >
                                    <option value="">Select archetype</option>
                                    <option  :value="archetype.archetype_name" v-for="archetype in archetypes">{{archetype.archetype_name}}</option>
                                </select>
                            </div>
                            <div class="col-auto">
                                <button type="submit" class="btn btn-warning">
                                    Search
                                </button>
                            </div>
                            <div class="col-auto">
                                <button type="reset" class="btn btn-dark" @click="$emit('search', 'reset')">
                                    Reset
                                </button>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
            
        </div>
        <div class="container bg-light p-5">
            <div class="row ">
                <div class="col ">
                    <h6 class="bg-dark text-light py-3 ps-2 fw-bold">
                        Found {{ cards.length }} cards
                    </h6>
                </div>
            </div>
            <div class="row">
                <div class="col-12 col-sm-6 col-md-4 col-lg-3 my-2" v-for="(card, i) in cards" :key="i">
                    <div class="bg  ">
                        <div class="image-container" v-for="(singleImage, i) in card.card_images" :key="singleImage.image_url">
                            <img :src="singleImage.image_url" >
                        </div>
                        <h5 class="text-uppecase text-light text-center py-1">
                            {{card.name}}
                        </h5>
                        <p class="text-center pb-3">
                            {{card.archetype}}
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
    main {
        background-color: #D48F38;
    }

  .bg {
    background-color: #D48F38;
  }

  .image-container{
    width: 100%;
    height: 90%;
    
    img{
        width: 100%;
        height: 100%;
    }
  }

</style>