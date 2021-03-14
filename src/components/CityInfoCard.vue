<template>
  <div>
    <h1>{{ search }}</h1>
  </div>
</template>

<script>
export default {
  name: "CityInfoCard",
  props: ['search'],
  created() {
    console.log("CityInfoCard.vue: " + this.search)
  }
}
</script>

<style>

</style>