<template>
  <div id="app">
    <h2>BAPSKIER'S JACKPOT</h2>
    <div class="jackpotcards-container">
      <JackpotCard
        v-for="(randomWord, index) in randomWords"
        :key="index"
        :randomWord="randomWord"
      />
    </div>
    <button @click="generateNewWords">SPIN!</button>
  </div>
</template>

<script>
import JackpotCard from './src/common/JackpotCard.vue';

export default {
  components: {
    JackpotCard,
  },
  data() {
      return {
          randomWords: ['are', 'you', 'ready'], // Initialize with empty strings
          counter: 0,
          words: ['butt', 'zin', 'hug', 'poopoo', 'butt', 'zin', 'baps', 'meow', 'baps', 'iskas', 'iskas']
      };
  },
  methods: {
      generateNewWord() {
          let resultIndex = Math.floor(Math.random() * 10);
          if((this.counter < 3 && resultIndex===5) || (this.counter < 2 && resultIndex===1)) resultIndex+=1

          return this.words[resultIndex];
      },
      generateNewWords() {
          this.counter++;
          if(this.counter%8===0) return this.randomWords = [this.words[5], this.words[5], this.words[5]]
          this.randomWords = this.randomWords.map(() => this.generateNewWord());
      },
  },
};
</script>

<style scoped>
h2 {
  color: red;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
.jackpotcards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
button {
  width: 30%;
  margin-top: 2rem;
  background-color: #5842ff;
  color: #ffffff;
  padding: 10px 20px;
  border-radius: 5px;
}
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100vh;
  background-image: url('./src/image/image.jpg');
  background-size: cover;
}
</style>
