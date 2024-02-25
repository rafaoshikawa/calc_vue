<script>
import { reactive } from "vue";

export default {
  setup() {
    const dados = reactive({
      numero1: 0,
      numero2: 0,
      operacao: "soma",
    });

    //funçao para fazer os calculos com base caso o usuario escolha os operadores
    function calcularResultado() {
      switch (dados.operacao) {
        case "soma":
          return dados.numero1 + dados.numero2;
        case "subtracao":
          return dados.numero1 - dados.numero2;
        case "multiplicacao":
          return dados.numero1 * dados.numero2;
        case "divisao":
          return dados.numero2 !== 0
            ? dados.numero1 / dados.numero2
            : "Indefinido";
        default:
          return 0;
      }
    }

    return { dados, calcularResultado };
  },
};
</script>
<template>
  <div id="app" class="container mt-5 bg-light custom-rounded">
    <h1 class="text-center pt-5">Calculadora Aritmética</h1>
    <div class="row">
      <div class="col-md-4">
        <label class="pt-3" for="numero1">Número 1:</label>
        <input
          v-model="dados.numero1"
          type="number"
          required
          placeholder="Digite seu número"
          class="form-control"
        />
      </div>
      <div class="col-md-4">
        <label class="pt-3" for="operacao">Operação:</label>
        <select v-model="dados.operacao" class="form-control">
          <option value="soma">Soma</option>
          <option value="subtracao">Subtração</option>
          <option value="multiplicacao">Multiplicação</option>
          <option value="divisao">Divisão</option>
        </select>
      </div>
      <div class="col-md-4">
        <label class="pt-3" for="numero2">Número 2:</label>
        <input
          v-model="dados.numero2"
          type="number"
          required
          placeholder="Digite seu número"
          class="form-control"
        />
      </div>
    </div>
    <div class="mt-3 pt-3 pb-3">
      <h4>Resultado: {{ calcularResultado() }}</h4>
    </div>
  </div>
</template>

<style scoped>
   .custom-rounded {
      border-radius: 10px; /* Tamanho do border-radius desejado */
    }
</style>
