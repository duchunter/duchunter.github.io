<template>
  <div>
    <div class="circle1">
      <div class="circle2">
        <div class="circle3" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Orbit',
}
</script>

<style scoped>
.circle1 {
  height: 85vw;
  width: 85vw;
  max-width: 85vh;
  max-height: 85vh;
  border-radius: 50%;
  border: 2px solid rgba(255, 255, 255, 0);
  border-left: 2px solid black;
  border-right: 2px solid black;
  animation: rotateClockwise 10s linear infinite;
  margin: 0 auto;
  position: relative;
  margin-top: 7.5vh;
}

.circle2 {
  height: 95%;
  width: 95%;
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0);
  border-top: 1px solid black;
  border-bottom: 1px solid black;
  position: absolute;
  top: 2.5%;
  left: 2.5%;
  animation: rotateCounterClockwise 5s linear infinite;
}

.circle3 {
  height: 95%;
  width: 95%;
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0);
  border-left: 1px solid black;
  position: absolute;
  top: 2.5%;
  left: 2.5%;
  animation: rotateClockwise 2.5s linear infinite;
}

@keyframes rotateClockwise {
  from {
    transform: rotate(0deg)
  }
  to {
    transform: rotate(360deg)
  }
}

@keyframes rotateCounterClockwise {
  from {
    transform: rotate(0deg)
  }
  to {
    transform: rotate(-360deg)
  }
}
</style>
