<template>
  <main>
      <h1>Simple Calculator</h1>
        <input v-model="n1" placeholder="First Number">
        <input v-model="n2" placeholder="Second Number">
        <br>
        <button v-on:click="result = parseFloat(n1) + parseFloat(n2)">+</button>
        <button v-on:click="result = parseFloat(n1) - parseFloat(n2)">-</button>
        <button v-on:click="result = parseFloat(n1) * parseFloat(n2)">*</button>
        <button v-on:click="divide()">/</button>
        <br>
        <h3>{{ result }}</h3>
  </main>
</template>

<script>
export default {
  data() {
      return {
          n1:"",
          n2:"",
          result: 0,
      }
  },
  methods: {
    divide() {
      if (parseFloat(this.n2) === 0) {
        this.result = "Undefined";
      } else {
        this.result = parseFloat(this.n1) / parseFloat(this.n2);
      }
    },
  },
};
</script>

<style>
body {
  background-color: #F7F7F7;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

main {
  text-align: center;
  background-color: #fff;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  max-width: 400px;
  margin: 0 auto;
}

input, button {
  padding: 5px;
  margin: 5px;
}

button {
  background-color: palevioletred;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: black;
}
</style>
