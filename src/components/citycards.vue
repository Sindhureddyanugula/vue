<template>
    <div class="city-card">
        <img class="background" src="../../public/newyork.jpeg" alt="City Background Image" v-if="id==0"/>
        <img class="background" src="../../public/chicago.jpeg" alt="City Background Image" v-if="id==1"/>
        <img class="background" src="../../public/houston.jpeg" alt="City Background Image" v-if="id==2"/>
        <img class="background" src="../../public/phoenix.jpeg" alt="City Background Image" v-if="id==3"/>
        <img class="background" src="../../public/san-francisco.webp" alt="City Background Image" v-if="id==4"/>

        <div class="content">
        <h1 class="city-name">{{ cityData[id].Cityname }}</h1>
        <div class="population">
          <p><strong>Female Population</strong> {{ cityData[id].FemaleCount }}</p>
          <p><strong>Male Population</strong> {{ cityData[id].MaleCount }}</p>

          <p><strong>Majors:</strong> {{cityData[id]['Majors(18_and_above)']}}</p>
          <p><strong>Minors:</strong> {{cityData[id]['Minors(Under_18)']}}</p>
        </div>

        <p class="population-index"><strong>Population Index:</strong> {{ cityData[id].PopulationIndex }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name : 'citycards',
    props : ['cityData','id']
  };
  </script>
  
  <style scoped>
  .city-card {
    width: 70vw; 
    max-width: 500px; 
    height: 350px; 
    margin: 20px;
    position: relative;
    overflow: hidden;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    color: #ffffff; 
  }
  
  .background {
    width: 100%;
    height: 100%;
    background-size: cover;
    background-position: center;
    position: absolute;
    filter: brightness(0.5);
    background-image: url('../../public/newyork.jpeg');
  }
  
  .content {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 20px;
    z-index: 1;
  }
  
  .city-name {
    font-size: 24px;
    margin-bottom: 10px;
    font-weight: bold;
  }
  
  .population {
    margin-bottom: 20px;
  }
  
  .population p {
    margin: 5px 0;
  }
  
  .population-index {
    margin-top: auto;
  }
  </style>
  