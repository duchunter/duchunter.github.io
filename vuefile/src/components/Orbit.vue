<template>
  <div class="circle">
  </div>
</template>

<script>
export default {
  name: 'Orbit',
}
</script>

<style scoped>
.circle {
  height: 80vw;
  width: 80vw;
  max-width: 80vh;
  max-height: 80vh;
  border-radius: 50%;
  border: 2px solid #bdbdbd;
  border-top: 2px solid black;
  border-bottom: 2px solid black;
  animation: rotate 10s linear infinite;
  margin: 0 auto;
  position: relative;
  margin-top: 10vh;
}


@keyframes rotate {
  from {
    transform: rotate(0deg)
  }
  to {
    transform: rotate(360deg)
  }
}
</style>
