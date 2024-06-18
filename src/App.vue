<script>
import axios from 'axios';
import Card from './components/Card.vue';

export default {
  name: 'App',
  components: {
    Card
    },
    data() {
    return {
      cards: []
    };
  },
  created() {
    this.fetchCards();
  },
  methods: {
    async fetchCards() {
      try {
        const response = await axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0');
        this.cards = response.data.data;
      } catch (error) {
        console.error('Error fetching the cards:', error);
      }
    }
    }
}
</script>

<template>
  <div id="app">
    <div class="cards-container">
      <Card v-for="card in cards" :key="card.id" :card="card" />
    </div>
  </div>
</template>

<style>
    .cards-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
    }
</style>