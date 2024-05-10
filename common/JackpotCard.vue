<template>
  <div class="card">
    <p>{{ randomWord }}</p>
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
  border: 5px solid #ccc;
  padding: 1rem;
  text-align: center;
  margin: 0.1rem;
  width: 5%;
}
</style>
