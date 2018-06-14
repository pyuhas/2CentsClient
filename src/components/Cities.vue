<template lang="html">

  <div class="each-listing">
    <body>
      <h1>{{city.city}}</h1>
      <p>{{city.trip_length}}</p>
      <p v-for='restaurant in city.restaurants'>{{restaurant}}</p>
      <p v-for='activity in city.activities'>{{activity}}</p>
      <button @click='deleteCity'>Delete</button>

      <form @submit.prevent='updateName()'>
        <input v-model='newCity' type="text">
        <button type='submit'>Change City</button>
      </form>
    </body>


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
      fetch(`https://warm-caverns-30232.herokuapp.com/cities/${this.city.id}`, {
        method: 'DELETE'
      }).then(response => {
        this.load()
      })
    },
    updateName(){
      fetch(`https://warm-caverns-30232.herokuapp.com/cities/${this.city.id}`, {
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

<style lang="css" scoped>

body {
  font-family: 'Roboto Mono', serif;
  /* display: flex; */
  justify-content: center;
}

.each-listing {
  text-align: center;
  background: blue;
  border-radius: 10px;
  border: 1px solid #999;
  margin: 60px;
  max-width: 370px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

}

h1 {
  font-size: 40px;
}

button {
  font-family: 'Roboto Mono';
  border: 2px solid black;
  background: white;
  padding: 10px 15px;
  margin: 0 10px;
  outline: 0;
  width: 60%;
  cursor: pointer;
}

</style>
