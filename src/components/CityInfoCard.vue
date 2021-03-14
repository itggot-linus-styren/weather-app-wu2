<template>
  <div class="card">
    <div class="summary">
      <h2>0°</h2>
      <h4>{{ city }}</h4>
    </div>
    <div class="weather">
      <h2>Rain</h2>
      <h4>Light rain</h4>
    </div>
    <div class="details">
      <button @click="$emit('goBack')">Back</button>
    </div>
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
    display: grid;
    min-width: 400px;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 2fr 1fr;
    grid-template-areas:
      "sm wt"
      "dt dt";
    background-color: rgba(232, 230, 227, 0.87);
    border-radius: 2em;
    padding: 2em;
    box-shadow: rgba(0, 0, 0, 0.3) 0px 0px 10px 1px;
  }

  h2, h4 {
    margin: 0 auto;
  }

  h4 {
    font-weight: 100;
  }

  .summary {
    grid-area: sm;
  }

  .weather {
    grid-area: wt;
  }

  .details {
    grid-area: dt;
  }
</style>