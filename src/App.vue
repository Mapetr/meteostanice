<template>
  <div id="app">
    <app-navbar />
    <router-view/>
  </div>
</template>

<script>
import AppNavbar from './components/AppNavbar';

export default {
  name: 'App',
  components: {
    AppNavbar,
  },
};
</script>

<style>
html, body {
  font-family: 'Roboto';
  margin: 0;
  padding: 0;
}
</style>
