<!-- App.vue -->
<template>
  <div id="app" class="container mt-5 custom-rounded bg-light">
    <h1 class="text-center pt-5">Calculadora Aritmética</h1>
    
    <input-data :dados="dados" />
    
    <result-display :calcularResultado="calcularResultado" />
  </div>
</template>

<script>
import { reactive } from "vue";
import InputData from "./InputData.vue";
import ResultDisplay from "./ResultDisplay.vue";

export default {
  components: {
    InputData,
    ResultDisplay,
  },
  setup() {
    const dados = reactive({
      numero1: 0,
      numero2: 0,
      operacao: "soma",
    });

    function calcularResultado() {
      switch (dados.operacao) {
        case "soma":
          return dados.numero1 + dados.numero2;
        case "subtracao":
          return dados.numero1 - dados.numero2;
        case "multiplicacao":
          return dados.numero1 * dados.numero2;
        case "divisao":
          return dados.numero2 !== 0 ? dados.numero1 / dados.numero2 : "Indefinido";
        default:
          return 0;
      }
    }

    return { dados, calcularResultado };
  },
};
</script>

<style scoped>
.custom-rounded {
  border-radius: 10px;
}
</style>
