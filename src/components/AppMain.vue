<template>
    <div>
      <main class="background-orange">
        <div class="container">
          <div class="dropdown my-3">
            <button
              class="btn btn-secondary dropdown-toggle"
              type="button"
              id="dropdownMenuButton"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              Select Card Type
            </button>
            <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton">
              <li v-for="type in cardTypes" :key="type">
                <a
                  class="dropdown-item"
                  href="#"
                  @click.prevent="fetchCards(type)"
                >
                  {{ type }}
                </a>
              </li>
            </ul>
          </div>
          <div class="card-container" id="card-container">
            <div v-for="card in filteredCards" :key="card.id" class="card">
              <img :src="card.card_images[0].image_url" :alt="card.name" />
              <h3>{{ card.name }}</h3>
              <p>{{ card.type }}</p>
            </div>
          </div>
        </div>
      </main>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        cards: [],
        filteredCards: [],
        cardTypes: [
          "Spell Card",
          "Trap Card",
          "Effect Monster",
          "Normal Monster",
          // Add more types as needed
        ],
      };
    },
    methods: {
      fetchCards(type) {
        fetch('https://db.ygoprodeck.com/api/v7/cardinfo.php')
          .then(response => response.json())
          .then(data => {
            this.cards = data.data;
            this.filteredCards = this.cards.filter(card => card.type === type);
          });
      }
    }
  };
  </script>
  
  <style lang="scss">
  .background-orange {
    background-color: #d48e39;
  }
  .card-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  .card {
    margin: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    background-color: #fff;
    width: 200px;
  }
  .card img {
    width: 100%;
  }
  .card h3 {
    font-size: 1.2em;
  }
  </style>