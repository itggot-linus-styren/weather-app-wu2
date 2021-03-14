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
    showCityInfo() {
      console.log("CityInfoCard.vue@showCityInfo: " + this.search)
    }
  },
  created() {
    console.log("CityInfoCard.vue@created: " + this.search)
  }
}
</script>

<style>

</style>