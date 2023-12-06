<template>
  <heroSection />
  <cardsList 
    :citydata = citiesData
  />
</template>

<script>
import heroSection from './components/heroSection.vue';
import citycards from './components/citycards.vue';
import cardsList from './components/cardsList.vue';

export default {
  name: 'App',
  components: {
    heroSection,
    citycards,
    cardsList
},
data (){
    return {
      citiesData : []
    }
  },
mounted() {
  fetch('https://citys-node-server.onrender.com/api')
        .then(response => response.json())
        .then(data => {
          this.citiesData = data;
        })
        .catch(error => console.error('Error fetching JSON data:', error));
  },
}
</script>

<style>
#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
