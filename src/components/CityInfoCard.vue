<template>
  <div class="card">
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
  .card {
    background-color: rgba(232, 230, 227, 0.87);
    border-radius: 2em;
    padding: 2em;
    box-shadow: rgba(0, 0, 0, 0.3) 0px 0px 10px 1px;
  }
</style>