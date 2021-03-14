<template>
  <div>
    <button @click="$emit('goBack')">Back</button>
    <h1>{{ city }}</h1>
  </div>
</template>

<script>
export default {
  name: "CityInfoCard",
  data() {
    return {
      city: ""
    }
  },
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