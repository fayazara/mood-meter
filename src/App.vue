<template>
  <div id="app" class="h-screen w-screen bg-gray-100">
    <Meter msg="How are you feeling today?" class="px-6 container mx-auto"/>
  </div>
</template>

<script>
import Meter from './components/Meter.vue';

export default {
  name: 'App',
  components: {
    Meter
  }
};
</script>

<style>
#app {
  font-family: -apple-system, BlinkMacSystemFont, Ubuntu, 'Segoe UI', Roboto, Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
