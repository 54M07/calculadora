<template>
    <div class="card">
      <div class="card-header text-center">
        <h1 class="mb-0">Calculadora</h1>
      </div>
      <div class="card-body">
        <div class="form-group">
          <input type="number" class="form-control" v-model="numero1" @input="calcular">
        </div>
        <div class="form-group">
          <select class="form-control" v-model="operacao" @change="calcular">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
          </select>
        </div>
        <div class="form-group">
          <input type="number" class="form-control" v-model="numero2" @input="calcular">
        </div>
        <div class="visor mb-4">{{ resultado }}</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Calculadora',
    data() {
      return {
        numero1: 0,
        numero2: 0,
        operacao: '+',
        resultado: 0
      };
    },
    methods: {
      calcular() {
        switch (this.operacao) {
          case '+':
            this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
            break;
          case '-':
            this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
            break;
          case '*':
            this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
            break;
          case '/':
            this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
            break;
          default:
            this.resultado = 0;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .card {
    max-width: 400px;
    border: none;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .card-body {
    padding: 20px;
  }
  
  .visor {
    border: 1px solid #ccc;
    padding: 10px;
    text-align: right;
    font-size: 20px;
  }
  </style>