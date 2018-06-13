<template>
  <main>
    <div id="app"/>
      <section>
        <MainPage :cities='cities'></MainPage>
      </section>
    </main>
</template>

<script>
import MainPage from './components/MainPage.vue'


export default {
  name: 'app',
  components: {
    MainPage
  },
  data (){
    return {
      cities: [],
      apiURL: 'http://localhost:3000/cities',
    }
  },
  mounted() {
    this.load()
  },
  methods: {
    load(){
      fetch(this.apiURL)
        .then(response => {
          return response.json()
      })
      .then(cities => {
        this.cities = cities
        // console.log(this.cities, "cities app")
      })
      .catch(err => {
        console.log.err
      })
  },
  deleteCities(){
  let objectData = new FormData(form)
  return fetch('https://warm-caverns-30232.herokuapp.com/cities/id', {
    method: 'DELETE',
    headers: new Headers({
      "Content-Type":'application/json'
    }),
    body: JSON.stringify({
      data: {
        city: objectData.get ('city'),
        trip_length: objectData.get ('trip_length'),
        restaurants: objectData.get ('restaurants'),
        activities: objectData.get ('activities')
      }
    })
  })
  .then(function(response){
    return response.json()
  })
}
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}
</style>
