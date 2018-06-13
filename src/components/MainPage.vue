<!-- HTML goes here -->
<template lang="html">
  <div class="MainPage">
    <head>
      <title>Where would you like to go?</title>
    </head>

    <body>
      <header class="site-header">
        <h1 class="site-header-1">Pick a city:</h1>
      </header>

      <select>
        <option value=''>Select a city:</option>
        <option v-for='city in cities' :value="city">{{city.city}}</option>
      </select>


      <main class="site-content">
        <div class="hero-image">
          <img src="http://www.bravotv.com/sites/nbcubravotv/files/field_blog_image/2017/04/jet-set-die-on-a-plane_0.jpg" style="height:500px; width:1200px" alt="dog-pic">
        </div>
      </main>

      <footer class="site-footer">
        <p>&copy; 2018 2Cents. All Rights Reserved.</p>
      </footer>
    </body>

  </div>
</template>

<!-- when you do fetch, you want it to alter
pass in prop?
populate with the matches -->


<script>
export default {
  name: 'MainPage',
  props: ['cities'],
}
</script>



<!-- //CSS goes here -->
<style scoped>
body {
display: flex;
flex-direction: column;
height: 100%;
width: 100%;
}
.site-header {
display: flex;
margin: -130px 20px 0px -30px;
flex-direction: column;
text-align: center;
justify-content: space-around;
width: 100%;
font-family: Comfortaa;
font-size: 50px;
color: #51bbd9;
position: fixed;
z-index: 40;
}

button {
  bottom: 20px;
  right: 680px;
  border-width: 1px;
  justify-content: space-around;
  background-color: grey;
  color: white;
  font-family: Comfortaa;
  font-size: 20px;
  text-align: center;
  position: fixed;
  cursor: wait;
  border-radius: 6px;
  text-decoration: none;
  border: none;
  color: white;
}

.site-footer {
position: fixed;
border-style: hidden;
border-width: 1px;
display: flex;
flex-direction: column;
font-family: Comfortaa;
font-size: 10px;
text-align: center;
bottom: 0%;
margin-left: 0;
width: 15%;
}

.hero-image {
position: fixed;
z-index: -1;
margin-top: 15.5%;
margin-left: 8%;
margin-bottom: 5px;
}

/* #form {
display: flex;
position: fixed;
margin: 70px 160px 120px 150px;
background-color: grey;
padding: 2%;
font-family: Comfortaa;
font-size: 25px;
text-align: center;
flex-direction: column;
width: 75%;
color: white;
border-radius: 25px;
} */

#type {
display: flex;
width: 260px;
font-size: 1px;
font-family: Comfortaa;
}

</style>
