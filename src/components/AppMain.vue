<template>
    <div>
      <main class="background-orange">
        <div class="card-container" id="card-container">
          
        </div>
      </main>
    </div>
  </template>
  
  <script>
  export default {
    mounted() {
      this.fetchCards();
    },
    methods: {
      fetchCards() {
        fetch('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
          .then(response => response.json())
          .then(data => this.displayCards(data.data));
      },
      displayCards(cards) {
        const container = document.getElementById('card-container');
        cards.forEach(card => {
          const cardElement = document.createElement('div');
          cardElement.classList.add('card');
          cardElement.innerHTML = `
            <img src="${card.card_images[0].image_url}" alt="${card.name}">
            <h3>${card.name}</h3>
            <p>${card.type}</p>
          `;
          container.appendChild(cardElement);
        });
      }
    }
  }
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