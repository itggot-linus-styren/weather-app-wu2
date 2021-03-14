<template>
  <div>
    <h1>{{ search }}</h1>
  </div>
</template>

<script>
export default {
  name: "CityInfoCard",
  props: ['search'],
  methods: {
    showCityInfo(city) {
      console.log("CityInfoCard.vue@showCityInfo: " + city)
      this.city = city;
    }
  },
  created() {
    this.$bus.on('searchCity', this.showCityInfo)
  }
}
</script>

<style>

</style>