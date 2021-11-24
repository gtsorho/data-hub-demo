<template>
  <div class="row text-light h-100">
    <div class="col-3 bg-dark pr-0">
      <leftpane />
    </div>
    <div class="col px-0">
      <navbar />
      <Card />
    </div>
  </div>
</template>

<script>
import navbar from "./components/navbar.vue"
import leftpane from "./components/leftpane.vue"
import Card from './components/Card.vue'

export default {
  name: 'App',
  components: {
    navbar,
    leftpane,
    Card
  }
}
</script>

<style>
html,body,#app{
  height: 100%;
}
</style>
