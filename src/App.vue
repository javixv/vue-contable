<script setup>
  import SplashScreen from './components/SplashScreen.vue'
  import { defineAsyncComponent   } from 'vue'

  const Home = defineAsyncComponent(() => {
  return new Promise((resolve, reject) => {
    // ...load component from server
    setTimeout(() => {
          resolve(import("./components/Home.vue"));
        }, 2500);
  })
})

 // Register the custom element.
 //customElements.define('my-vue-element', MyVueElement)
</script>

<template>

  
  <Suspense>
    <template #default><Home /></template>
    <template #fallback><SplashScreen /></template>
  </Suspense>
</template>

<style scoped>
html,
body,
.app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}
* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}
</style>
