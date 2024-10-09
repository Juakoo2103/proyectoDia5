<template>
  <form>
      <div>
        <label>Título de la tarjeta: </label>
        <input type="text" v-model="cardTitle"/>
      </div>

      <div>
        <label>Chip SRC: </label>
        <input type="text" v-model="chipSrc" />
      </div>

      <div>
        <label>Número: </label>
        <input type="number" v-model="cardNum">
      </div>

      <div>
        <label>Fecha de expiración: </label>
        <input type="date" v-model="expDate" />
      </div>

      <div>
        <label>Propietario: </label>
        <input type="text" v-model="name"/>
      </div>

      <div>
        <label>Tipo de tarjeta SRC: </label>
        <input type="text" v-model="cardType"/>
      </div>
    </form>

    <div class="carnet">
      <h3>{{ cardTitle }}</h3>
      <img width="40" :src="chipSrc" alt="Chip Image" />
      <div>
        <h2>{{ cardNum }}</h2>
        <span>Fecha Exp: <b>{{ expDate }}</b></span>
      </div>
      <footer>
        <span>{{ name }}</span>
        <img :src="cardType" width="60" />
      </footer>
    </div>

</template>

<script>

import chipImage from '../assets/chip.png'
import cardImage from '../assets/visa.png'

export default {
  name: 'Card',
  data() {
      return {
          name: "",
          cardTitle: "",
          cardNum: "",
          expDate: "",
          chipSrc: chipImage,
          cardType: cardImage,  
      };
  }
};
</script>

<style scoped>
  * {
      margin: 0;
    }
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 60vh;
      font-size: 10px;
      font-family: sans-serif;
    }

    #app {
      display: flex;
      gap: 40px;
    }
    form {
      padding: 18px;
      border-radius: 20px;
      border: ridge 1px;
      box-shadow: 1px 1px 1px 1px gray;
      font-weight: bold;
      display: flex;
      flex-direction: column;
      gap: 15px;
      justify-content: center;
    }
    form div {
      display: grid;
      grid-template-columns: 100px 200px;
      align-items: center;
      gap: 5px;
    }

    form div label {
      text-align: right;
    }

    .carnet {
      width: 400px;
      height: 230px;
      background: #1c1a1e;
      color: white;
      border-radius: 20px;
      padding: 20px;
      box-shadow: 0px 0px 10px 2px black;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    h3 {
      font-size: 20px;
    }

    h2 {
      font-size: 30px;
      letter-spacing: 10px;
      margin-bottom: 15px;
      text-shadow: 0px 0px 1px gold;
      font-family: Times;
    }

    b {
      font-size: 16px;
    }

    footer {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      font-weight: bold;
      font-size: 18px;
      text-transform: uppercase;
      font-style: italic;
    }
</style>
