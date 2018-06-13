<template>
  <main>
    <div id="app"/>
      <section>
        <MainPage :load='load' :cities='cities'></MainPage>
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
      id: [],
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
      })
      .catch(err => {
        console.log.err
      })
  },

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
