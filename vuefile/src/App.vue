<template>
  <div id="app">
    <div class="container">
      <NavBar />
      <Clock />
      <Orbit />
    </div>
  </div>
</template>

<script>
import Orbit from './components/Orbit'
import Clock from './components/Clock'
import NavBar from './components/NavBar'
export default {
  name: 'App',
  components: {
    Clock, Orbit, NavBar
  }
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
}
</style>
