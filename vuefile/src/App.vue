<template>
  <div id="app">
    <div class="container">
      <NavBar />
      <LandingScreen />
    </div>
  </div>
</template>

<script>
import LandingScreen from './containers/LandingScreen'
import NavBar from './components/NavBar'
export default {
  name: 'App',
  data() {
    return {
      view: 'LandingScreen'
    }
  },

  components: {
    NavBar, LandingScreen,
  },
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}

.container {
  border: 0.1px solid rgba(255, 255, 255, 0.5);
  height: 100vh;
  width: 100%;
  background-color: rgba(255, 255, 255, 0.5);
  position: relative;
}

#app {
  margin: 0;
  padding: 0;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100%;
  min-height: 100%;
  height: 100vh;
  background-image: url('https://images.pexels.com/photos/355747/pexels-photo-355747.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940');
  background-position: bottom;
  background-repeat: no-repeat;
  background-size: cover;
  overflow: hidden;
  background-color: black;
}

#app:hover {
  animation: animate .2s infinite;
}

@keyframes animate {
  0% {
    background-position: 0 0;
    filter: hue-rotate(0deg);
  }
  10% {
    background-position: 1vh 0;
  }
  20% {
    background-position: -1vh 0;
  }
  30% {
    background-position: 1vh 0;
  }
  40% {
    background-position: -1vh 1vw;
  }
  50% {
    background-position: -1vh 0;
  }
  60% {
    background-position: -1vh 0;
  }
  70% {
    background-position: 0 1vw;
  }
  80% {
    background-position: -1vh -1vw;
  }
  100% {
    background-position: 0 0;
    filter: hue-rotate(360deg);
  }
}
</style>
