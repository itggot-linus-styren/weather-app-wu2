<template>
  <div class="flex">
    <!--
      type="search" och type="text" gör ingen skillnad men det är tydligare
      att detta inputfält är ett sökfält. Se också:
      https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/search
    -->      
    <input data-cy="city" class="input" type="search" placeholder="Köttkulla..">
    <button data-cy="search">🔍</button>
  </div>
</template>

<script>
export default {

}
</script>

<style>
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