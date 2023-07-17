<script>
    export default {
        name: "MainComponent",
        data() {
            return {

            }
        },
        methods: {

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
        <div class="container bg-light">
            hello!
        </div>
    </main>
</template>

<style lang="scss" scoped>
    main {
        background-color: #D48F38;
    }
</style>