<template>
    <div>
      <main class="background-orange">
        <div class="card-container" id="card-container">
          
        </div>
      </main>
    </div>
  </template>
  
  <script>
  
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