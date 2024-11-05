<template>
  <div class="card">
    <div>{{ randomWord }} 234hufdsf</div>
  </div>
</template>

<script>
export default {
  props: {
    randomWord: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.card {
  border: 5px solid rgb(52, 250, 200);
  padding: 1rem 0.5rem;
  text-align: center;
  margin: 0.5rem;
  max-width: 15%;
  width: 2rem;
  color: white;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
</style>
