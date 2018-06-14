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

      <Cities v-for='city in cities' :load='load' :key='city.id' :city='city'/>

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
import Cities from './Cities.vue'


export default {
  components: {
    Cities
  },
  data() {
    return {
      // id: this.city.id
    }
  },
  name: 'MainPage',
  props: ['cities', 'load'],
}
</script>



<!-- //CSS goes here -->
<style scoped>
/* body {
display: flex;
flex-direction: column;
height: 100%;
width: 100%;
} */
.site-header {
display: flex;
height: 180px;
margin: -50px 20px 0px -30px;
flex-direction: column;
text-align: center;
justify-content: space-around;
width: 100%;
font-style: normal;
font-family: Comfortaa;
font-size: 50px;
color: #51bbd9;
position: fixed;
z-index: 40;
}

/* .site-content {
justify-content: center;
 height: auto;
  width: auto;
} */

/* .img {
  justify-content: center;
  z-index: -5;
  height: 100%;
} */


.site-footer {
position: fixed;
border-style: hidden;
border-width: 1px;
display: flex;
flex-direction: column;
font-family: Comfortaa;
font-size: 15px;
text-align: center;
bottom: 0%;
margin-left: 0;
width: 97%;
}

#type {
display: flex;
width: 260px;
font-size: 1px;
font-family: Comfortaa;
}

</style>
