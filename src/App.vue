<template>
  <Navigation />
  <router-view/>
</template>

<script>
import  Navigation  from '@/components/Navigation.vue';

export default {
  components: {
    Navigation
  }
}
</script>


<style>

@import url('https://fonts.googleapis.com/css2?family=League+Gothic&display=swap');

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>
