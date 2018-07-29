<template>
  <div class="clock-container"  @mouseover="changeText" @click="changeText">
    <img class="clock-logo" src="../assets/logo.png">
    <div class="clock-content">
      <div class="clock-character" v-for="char in text">
        {{char}}
      </div>
    </div>
  </div>
</template>

<script>
const quote = 'ADAPT IMPROVE EVOLE';
const shuffleSpeed = 60;
const changeTextSpeed = 3000;

export default {
  name: 'Clock',
  data() {
    return {
      text: quote.split(''),
      clockInterval: null,
      shuffleInterval: null,
      showQuote: true,
      isShuffling: false,
    }
  },

  methods: {
    getLocalTime() {
      return new Date().toLocaleDateString('en-GB', {
        day: '2-digit',
        month: 'short',
        year: 'numeric',
        hour: '2-digit',
        minute: '2-digit',
      }).replace(',', '  ').toUpperCase();
    },

    shuffle(finalText) {
      clearInterval(this.clockInterval);
      this.isShuffling = true;
      this.shuffleInterval = setInterval(() => {
        this.text = this.text.map((char, index) => {
          if (char != finalText[index]) {
            if (char == ' ') {
              return '/';
            }

            let current = char.charCodeAt(0) + 1;
            if (current == 59) current = 65;
            if (current == 90) current = 32;
            return String.fromCharCode(current);
          }

          return char;
        });
      }, shuffleSpeed);
    },

    changeText() {
      // If text is shuffling, nothing happen
      if (this.isShuffling) {
        return;
      }

      // Start shuffling
      this.shuffle(this.showQuote ? this.getLocalTime() : quote);

      // Max shuffling time = 1s
      setTimeout(() => {
        this.showQuote = !this.showQuote;
        if (!this.showQuote) {
          // If displaying clock, reset display every 1s
          this.text = this.getLocalTime().split('');
          this.clockInterval = setInterval(() => {
            this.text = this.getLocalTime().split('');
          }, 30000);
        } else {
          clearInterval(this.clockInterval);
          this.text = quote.split('');
        }

        // Shuffle complete
        clearInterval(this.shuffleInterval);
        this.isShuffling = false;
      }, changeTextSpeed);
    }
  }
}
</script>

<style scoped>
.clock-container {
  height: 50vw;
  width: 100%;
  max-height: 50vh;
  text-align: center;
  cursor: pointer;
  position: absolute;
  z-index: 100;
  top: 20vh;
}

.clock-content {
  font-family: Orbitron;
  font-size: 3.5vw;
}

.clock-character {
  width: 3.6vw;
  max-width: 3.6vh;
  display: inline-block;
}

.clock-logo {
  height: 30vw;
  width: 30vw;
  max-width: 30vh;
  max-height: 30vh;
  margin-bottom: 10vh;
}

@media screen and (min-width: 800px) {
  .clock-content {
    font-size: 3.6vh;
  }
}

@media screen and (max-height: 550px) {
  .clock-content {
    font-size: 2.6vh;
  }
}

@media screen and (max-width: 600px) {
  .clock-logo {
    margin-bottom: 5vw;
  }
}

</style>
