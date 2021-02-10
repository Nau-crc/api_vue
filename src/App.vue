<template>
  <div id="app">
    <dishesList @itemClicked="addToCart" />
  </div>
</template>

<script>
import dishesList from './components/dishesList.vue'

export default {
  name: 'App',
  components: {
    dishesList,
  },
  methods: {
    addToCart(dishes) {
      console.log(dishes)
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
