<template>
  <div class="row text-light h-100" style="flex-wrap: inherit;">
    <div class="col-3 leftpane bg-dark pr-0">
      <leftpane />
    </div>
    <div class="col px-0" >
      <Navbar />
      <div class="container">
        <div class="row row-cols-1 row-cols-sm-2 row-cols-md-4">
           <Card v-for='cityWeather in citiesWeather' :key="cityWeather.id" :weather="cityWeather"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/navbar.vue"
import leftpane from "./components/leftpane.vue"
import Card from './components/Card.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Navbar,
    leftpane,
    Card
  },
  data() {
    return {
      citiesWeather : []
    }
  },
  
  created() {
  
    axios
    .get('http://api.openweathermap.org/data/2.5/box/city',{
      params : {
        bbox: '-2.731130,4.856721,0.501007,10.926089,7',
        appid: 'b9564e9e1381bcf8925e4cfc654c44f1'
      }
    })
    .then(response => {
      this.citiesWeather=response.data.list
      console.log(this.citiesWeather)
    })
    .catch(error => {
      console.log(error)
    })
  },
}
</script>

<style>
html,body,#app{
  height: 100%;
}
.leftpane{
    width: 15% !important;
    padding-right: 0px !important;
    padding-left: 0px !important;
}
</style>
