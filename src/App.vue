<template>
  <div class="row text-light h-auto" style="flex-wrap: inherit; min-height: -webkit-fill-available;">
    <div class="col-3 leftpane bg-dark pr-0" style="min-width: fit-content;">
      <leftpane />
    </div>
    <div class="col px-0" >
      <Navbar :showOnNav="recordLength"/>
      <div class="container">
        <div class="row row-cols-1 row-cols-sm-2 row-cols-md-4">
          <Card v-for='cityWeather in display' :key="cityWeather.id" :weather="cityWeather"/>
        </div>
      </div>
      <!-- footer -->
      <Footer :page="page" :pages="pages" v-on:updateHandler='update_handler($event)' />
      <!-- end of footer -->
    </div>
  </div>
</template>

<script>
import Navbar from "./components/navbar.vue"
import leftpane from "./components/leftpane.vue"
import Card from './components/Card.vue'
import Footer from './components/footer.vue'
import axios from 'axios'



export default {
  name: 'App',
  components: {
    Navbar,
    leftpane,
    Card,
    Footer
  },
  data() {
    return {
      citiesWeather : [],
      page: 1,
      perPage: 10,
      pages: 0,
      recordLength:0
    }
  },
  
  created() {
    axios
    .get('http://api.openweathermap.org/data/2.5/box/city',{
      params : {
        bbox: '-2.731130,4.856721,0.501007,10.926089,11',
        appid: 'b9564e9e1381bcf8925e4cfc654c44f1'
      }
    })
    .then(response => {
      this.citiesWeather=response.data.list
      this.recordLength =  response.data.list.length + " Towns Showing"
      this.pages = Math.ceil(response.data.list.length/this.perPage)
      console.log(this.citiesWeather)

    })
    .catch(error => {
      console.log(error)
    })
  },
  computed: {
    display() {
      const startIndex = this.perPage * (this.page - 1);
      const endIndex = startIndex + this.perPage;
      return this.citiesWeather.slice(startIndex, endIndex);
    }
  },
  methods: {
    update_handler(page){
      this.page = page
    }
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
*, ::after, ::before {
    box-sizing: border-box;
    margin-bottom: inherit;
}
</style>
