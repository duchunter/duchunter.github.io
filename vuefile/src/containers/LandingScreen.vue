<template>
  <div>
    <Clock />
    <Orbit />
  </div>
</template>

<script>
import Orbit from '../components/Orbit'
import Clock from '../components/Clock'

export default {
  name: 'LandingScreen',
  components: {
    Orbit, Clock
  }
}
</script>

<style scoped>

</style>
