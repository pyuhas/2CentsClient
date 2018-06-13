<template lang="html">

  <div class="each-listing">
    <h1>{{city.city}}</h1>
    <p>{{city.trip_length}}</p>
    <p v-for='restaurant in city.restaurants'>{{restaurant}}</p>
    <p v-for='activity in city.activities'>{{activity}}</p>
    <button @click='deleteCity'>Delete</button>

    <form @submit.prevent='updateName()'>
      <input v-model='newCity' type="text">
      <button type='submit'>Change City</button>
    </form>

  </div>

</template>

<script>
export default {
  props: ['city', 'load'],
  data() {
    return {
      newCity: ''
    }
  },
  methods: {
    deleteCity(){
      fetch(`http://localhost:3000/cities/${this.city.id}`, {
        method: 'DELETE'
      }).then(response => {
        this.load()
      })
    },
    updateName(){
      fetch(`http://localhost:3000/cities/${this.city.id}`, {
        method: 'PUT',
        body: JSON.stringify({
          city: this.newCity
        }),
        headers: new Headers({"Content-type": "application/json"})
      }).then(response => {
        console.log('clicked');
        this.load()
      })
    },
    }
  }


</script>

<style lang="css">
</style>
