<template>
  <div>
    <h1>JACKPOT</h1>
    <button @click="generateNewWords">SPIN!</button>
    <div class="jackpotcards-container">
      <JackpotCard
        v-for="(randomWord, index) in randomWords"
        :key="index"
        :randomWord="randomWord"
        />
      </div>
    </div>
</template>

<script>
import JackpotCard from './common/JackpotCard.vue';

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
          const resultIndex = Math.floor(Math.random() * 10);
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
.jackpotcards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
