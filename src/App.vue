<template>
  <div>
    <h1>Weather App</h1>
    <div class="flex">
      <!--
        type="search" och type="text" gör ingen skillnad men det är tydligare
        att detta inputfält är ett sökfält. Se också:
        https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/search
      -->      
      <input data-cy="city" class="input" type="search" placeholder="Köttkulla..">
      <button data-cy="search">🔍</button>
    </div>
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
  display: flex;
  align-items: center;
  justify-content: center;
  height: calc(100vh - 5em);
  font-size: 24px;
}

.flex {
  display: flex;
  max-width: 400px;
}

.input {
  width: 100%;
  padding: 8px 10px;
  border: 1px solid #32485F;
  flex: 1;
}
</style>
