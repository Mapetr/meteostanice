<template>
    <nav>
        <h1>METEOSTANICE</h1><h2>{{ time }}</h2>
    </nav>
</template>

<script>
const dayjs = require('dayjs');

    export default {
        name: 'navbar',
        data() {
            return {
                time: '',
            }
        },
        methods: {
            setTime: function () {
                const time = dayjs().format('HH:mm:ss');
                this.time = time;
            },
        },
        mounted() {
            this.$nextTick(function() {
                window.setInterval(() => {
                    this.setTime();
                },1000);
            });
        },
    }
</script>

<style scoped>
nav {
    background-color: lightslategray;
    width: 100%;
    height: 50px;

    display: flex;
    align-items: center;
}

h1 {
    margin: 0 0 0 25px;
}

h2 {
    width: 100%;
    text-align: right;
    margin: 0 25px 0 0;
}

</style>
