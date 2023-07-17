<script>
   
    export default {
        name: "HeaderComponent",
        data() {
            return {
               
            }
        },
        methods: {

        }
    }
</script>

<template>
    <header class="py-3">
        <div class="container">
            <div class="row">
                <div class="col-1">
                    <div class="logo-container">
                        <img src="https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="">
                    </div>
                </div>
                <div class="col">
                    <h1>
                        YU-GI-OH API
                    </h1>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
    .logo-container {
        width: 100px;
        height: 50px;

        img{
            width: 100%;
            height: 100%;
        }
    }
</style>