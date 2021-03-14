<template>
  <div>
    <h1>Weather App</h1>
    <!--
      type="search" och type="text" gör ingen skillnad men det är tydligare
      att detta inputfält är ett sökfält. Se också:
      https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/search
    -->
    <input data-cy="city" type="search" placeholder="Köttkulla..">
    <button data-cy="search">🔍</button>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
