<script>
    export default {
        name: "MainComponent",
        data() {
            return {
                
            }
        },
        methods: {

        },

        props: {
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
            <div class="row py-4">
                <div class="col-2">
                    <select class="form-select" aria-label="Alien">
                        <option selected>Alien</option>
                        <option value="1">One</option>
                        <option value="2">Two</option>
                        <option value="3">Three</option>
                    </select>
                </div>
            </div>
        </div>
        <div class="container bg-light p-5">
            <div class="row ">
                <div class="col ">
                    <h6 class="bg-dark py-3 ps-2">
                        Found {{ cards.length }} cards
                    </h6>
                </div>
            </div>
            <div class="row">
                <div class="col-12 col-sm-6 col-md-4 col-lg-3 my-2" v-for="(card, i) in cards" :key="i">
                    <div class="bg ">
                        <div>
                        <img :src="card.card_images" :alt="card.name">
                        </div>
                        <h5>
                            {{card.name}}
                        </h5>
                        <p>
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
    height: 400px;
  }

  h6 {
    color: white;
    font-weight: bold;
  }

</style>