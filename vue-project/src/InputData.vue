<!-- componente para a entrada de dados -->

<script>

export default {
  props: ['dados'],
};

</script>
<template>
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
</template>

