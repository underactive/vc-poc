<template>
  <div id="app">
    <!-- Sidebar/menu -->
    <nav class="w3-sidebar w3-collapse w3-white w3-animate-left" style="z-index:3;width:300px;" id="mySidebar"><br>
      <div class="w3-container">
        <a href="#" @click="w3_close()" class="w3-hide-large w3-right w3-jumbo w3-padding w3-hover-grey" title="close menu">
          <i class="fa fa-remove"></i>
        </a>
        <img src="https://i.imgur.com/3hwbgRs.png" style="width:45%;" class="w3-round"><br><br>
      </div>
      <div class="w3-bar-block">
        <router-link to="/"><i class="fa fa-th-large fa-fw w3-margin-right"></i>CHARACTERS</router-link><br />
        <router-link to="/about"><i class="fa fa-user fa-fw w3-margin-right"></i>ABOUT</router-link>
      </div>
    </nav>

    <!-- Overlay effect when opening sidebar on small screens -->
    <div class="w3-overlay w3-hide-large w3-animate-opacity" @click="w3_close()" style="cursor:pointer" title="close side menu" id="myOverlay"></div>

    <!-- !PAGE CONTENT! -->
    <div class="w3-main" style="margin-left:300px">

      <!-- Header -->
      <header id="portfolio">
        <!-- <a href="#"><img src="https://www.w3schools.com/w3images/avatar_g2.jpg" style="width:65px;" class="w3-circle w3-right w3-margin w3-hide-large w3-hover-opacity"></a> -->
        <span class="w3-button w3-hide-large w3-xxlarge w3-hover-text-grey" @click="w3_open()"><i class="fa fa-bars"></i></span>
        <div class="w3-container">
        <h1><b>Non-page-refreshing list re-render demo</b></h1>
        </div>
      </header>

      <router-view/>

      <!-- Footer -->
      <footer class="w3-container w3-padding-32 w3-dark-grey">
      <div class="w3-row-padding">
        <h3>FOOTER</h3>
        <p>Footery stuff here</p>
      </div>
      </footer>

      <div class="w3-black w3-center w3-padding-24">Powered by <a href="https://www.w3schools.com/w3css/default.asp" title="W3.CSS" target="_blank" class="w3-hover-opacity">w3.css</a></div>

    <!-- End page content -->
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },

  async created () {
  },

  methods: {
    w3_open () {
      document.getElementById('mySidebar').style.display = 'block'
      document.getElementById('myOverlay').style.display = 'block'
    },

    w3_close () {
      document.getElementById('mySidebar').style.display = 'none'
      document.getElementById('myOverlay').style.display = 'none'
    }
  }
}
</script>

<style lang="scss">
</style>
