<template>
  <div>
    <h1>Weather App</h1>
    <CitySearchField @searchCity="onSearchCity" />
    <CityInfoCard ref="city" :search="search" />
  </div>
</template>

<script>
import CityInfoCard from './components/CityInfoCard.vue';
import CitySearchField from './components/CitySearchField.vue';

export default {
  name: 'App',
  data() {
    return {
      search: ""
    }
  },
  methods: {
    onSearchCity(search) {
      console.log("Du sökte på " + search);
      this.search = search;
      setTimeout(() => {
        this.$refs.city.showCityInfo();
      }, 1);
    }
  },
  components: { CityInfoCard, CitySearchField }
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
</style>
