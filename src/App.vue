<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input type="number" v-model.number="numero1" />
      <select v-model="operacao">
        <option value="+">Soma</option>
        <option value="-">Subtração</option>
        <option value="*">Multiplicação</option>
        <option value="/">Divisão</option>
      </select>
      <input type="number" v-model.number="numero2" />
    </div>
    <h2>Resultado: {{ resultado }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.numero1 + this.numero2;
        case '-':
          return this.numero1 - this.numero2;
        case '*':
          return this.numero1 * this.numero2;
        case '/':
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}
input {
  margin: 10px;
}
</style>