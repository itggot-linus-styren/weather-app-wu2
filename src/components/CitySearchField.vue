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
import config from '@/appConfig.js';

export default {
  name: "CitySearchField",
  data() {
    return {
      search: ""
    }
  },
  methods: {
    onSearchClick() {
      const url = `http://api.openweathermap.org/data/2.5/weather?q=Köttbulle&appid=${config.apiKey}`;
      /*
       * Eftersom det tar tid att hämta data från externa resurser så måste vi 
       * köra fetch asynkront, dvs i bakgrunden utan att blockera webbläsaren.
       * 
       * Ifall vi hade kört detta synkront hade det inte gått att göra något
       * innan vi får tillbaka ett svar. Prova att köra denna koden för att se
       * skillnaden:
       
      let request = new XMLHttpRequest();
      request.open('GET', url, false); // `false` makes the request synchronous
      request.send(null);

       * Fetch returnerar ett Promise som vi ger en callback funktion som
       * körs när vi får tillbaka ett svar.
       */
      fetch(url).then((response) => {
        if (!response.ok) {
          // Ifall vi inte fick en 2xx response, avbryt kedjan här (reject)
          throw new Error("No matching location.");
        } else {
          // Annars konverterar vi svaret till ett JS objekt
          return response.json();
        }        
      }).then((cityInfo) => {
        console.log(cityInfo);
        this.$bus.emit('searchCity', `${cityInfo.name}, ${cityInfo.sys.country}`);
      }).catch((reason) => {
        alert(reason);
      })
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