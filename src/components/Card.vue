<template>
        <div class="col cards-list">
            <div class="card">
              <div class="card-body my-2">
                <h4 class="card-title ">{{weather.name}}</h4>
                <div class="row mt-4">
                  <div class="col">
                    <img :src="tempImg">
                    <p class="fw-bolder font-monospace text-muted ps-1">{{weather.main.temp}}</p>
                  </div>
                  <div class="col">
                    <img :src="humidityImg">
                    <p class="fw-bolder font-monospace text-muted ps-1">{{weather.main.humidity}}</p>
                  </div>
                  <div class="col">
                    <img :src="pressureImg">
                    <p class="fw-bolder font-monospace text-muted ps-1">{{weather.main.pressure}}</p>
                  </div>
                  <div class="col">
                    <img :src="windImg">
                    <p class="fw-bolder font-monospace text-muted ps-1">{{weather.wind.speed}}</p>
                  </div>
                </div>
              </div>
            </div>
        </div>        
</template>

<script>

export default {
    name: "Card",
    data() {
      return {
        tempImg: require('../assets/thermometer.png'),
        humidityImg: require('../assets/humidity.png'),
        pressureImg: require('../assets/pressure-gauge.png'),
        windImg: require('../assets/wind-socket.png')
      }
    },
    props: {
      weather: Object
    }
    
}
</script>

<style scoped>
.cards-list {
  z-index: 0;
  /* width: 100%; */
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.col img{
  width: 30px;
}
.col p{
  margin-top: 15px;
}
.card-body{
  padding-bottom: 2px;
    padding-top: 2px;
}
.card {
  color: black;
  margin: 30px auto;
  width: 500px;
  height: auto;
  border-radius: 20px;
  box-shadow: 0px 1px 5px 5px rgb(0 0 0 / 6%), -2px 2px 21px 0px rgb(0 0 0 / 16%);
  cursor: pointer;
  transition: 0.4s;
}

.card .card_image {
  width: inherit;
  height: inherit;
  border-radius: 40px;
}

.card .card_image img {
  width: inherit;
  height: inherit;
  border-radius: 20px;
  object-fit: cover;
}


.card:hover {
  transform: scale(1.03, 1.03);
  box-shadow: 0px 0px 8px 6px rgb(0 0 0 / 20%), -5px -5px 15px -7px rgb(0 0 0 / 17%);
}

@media all and (max-width: 500px) {
  .card-list {
    /* On small screens, we are no longer using row direction but column */
    flex-direction: column;
  }
}
</style>