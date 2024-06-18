  
<script>
  export default {
      name: 'Card',
    props: {
        card: {
            type: Object,
            required: true
      }
    }
  }
</script>
  
<template>
    <div class="card">
        <img :src="card.card_images[0].image_url" alt="Card Image" class="card-img">
        <div class="card-details">
            <h2>{{ card.name }}</h2>
            <p>{{ card.type }}</p>
            <p>{{ card.race }}</p>
        </div>
    </div>
</template>


<style scoped>
  .card {
    border: 1px solid #ddd;
    border-radius: 5px;
    overflow: hidden;
    margin: 10px;
    width: 200px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }
  .card-img {
    width: 100%;
    height: auto;
  }
  .card-details {
    padding: 10px;
    text-align: center;
  }
  .card-details h2 {
    font-size: 1.2em;
    margin: 10px 0;
  }
  .card-details p {
    margin: 5px 0;
    color: #555;
  }
</style>
  