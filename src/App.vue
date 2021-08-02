<template>
    <h1> Мой Vue.js</h1>
    <div v-for="person in info">
        {{person.id}} {{person.name}} {{person.data}}
    </div>
</template>

<script>
    const axios = require('axios').default;

    export default {
        data() {
            return {
                info: null
            }
        },
        mounted() {
            axios
                .get('http://localhost:8079/api')
                .then(response => (this.info = response.data));
        }
    }
</script>

<style>

</style>
