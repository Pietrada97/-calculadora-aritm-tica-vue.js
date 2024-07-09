<template>
  <div id="app">
    <div class="calculator">
      <h1>Calculadora Aritmética</h1>
      <div class="inputs">
        <input type="number" v-model.number="num1" placeholder="Número 1" />
        <select v-model="operation">
          <option value="add">+</option>
          <option value="subtract">-</option>
          <option value="multiply">*</option>
          <option value="divide">/</option>
        </select>
        <input type="number" v-model.number="num2" placeholder="Número 2" />
      </div>
      <div class="result">
        <h2>Resultado: {{ result }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.num1 + this.num2;
        case 'subtract':
          return this.num1 - this.num2;
        case 'multiply':
          return this.num1 * this.num2;
        case 'divide':
          return this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.calculator {
  display: inline-block;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
}

.inputs {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-bottom: 20px;
}

.result {
  font-size: 1.5em;
  color: #333;
}
</style>
