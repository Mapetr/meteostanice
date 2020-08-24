<template>
    <div>
        <home-line v-bind:leftName="'Temperature'" v-bind:left='temperature' v-bind:rightName="'Humidity'" v-bind:right='humidity' />
        <home-line v-bind:leftName="'Dewpoint'" v-bind:left='dewpoint' v-bind:rightName="'Pressure'" v-bind:right='pressure' />
        <home-line v-bind:leftName="'Wind Speed'" v-bind:left='windspeed' v-bind:rightName="'Wind Direction'" v-bind:right='winddirection' />
        <home-line v-bind:leftName="'Rainfall'" v-bind:left='rainfall' v-bind:rightName="''" v-bind:right='null' />
    </div>
</template>

<script>
import HomeLine from './HomeLine';

    export default {
        name: 'Home',
        data() {
            return {
                temperature: '-1',
                dewpoint: '-1',
                humidity: '-1',
                pressure: '-1',
                windspeed: '-1',
                winddirection: '-1',
                rainfall: '-1',
            }
        },
        methods: {
            async fetchdata() {
                const res = await fetch(`10.0.0.105:3000/v1/latest`);
                const items = await res.json();
                this.temperature = items.temperature;
                this.humidity = items.humidity;
                this.dewpoint = items.dewpoint;
                this.pressure = items.pressure;
                this.windspeed = items.windspeed;
                this.winddirection = items.winddirection;
                this.rainfall = items.rainfall;
            }
        },
        mounted() {
            var update = setInterval(this.fetchdata(), 1000);
        },
        components: {
            HomeLine,
        },
    }
</script>

<style scoped>

</style>