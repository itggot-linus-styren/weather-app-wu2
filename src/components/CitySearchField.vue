<template>
  <div class="flex">
    <!--
      type="search" och type="text" gör ingen skillnad men det är tydligare
      att detta inputfält är ett sökfält. Se också:
      https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/search
    -->      
    <input
      data-cy="city"
      class="input"
      type="search"
      placeholder="Köttkulla.."
      @keyup.enter="onSearchClick"
      v-model="search"
    />
    <button data-cy="search" @click="onSearchClick">🔍</button>
  </div>
</template>

<script>
export default {
  name: "CitySearchField",
  data() {
    return {
      search: ""
    }
  },
  methods: {
    onSearchClick() {
      console.log(this.search);
    }
  }
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