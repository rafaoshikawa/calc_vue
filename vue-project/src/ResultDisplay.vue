<!-- componente para a exibição do resultado -->
<template>
  <div class="mt-3 pt-3 pb-3">
    <h4>Resultado: {{ calcularResultado() }}</h4>
  </div>
</template>

<script>
export default {
  props: ['calcularResultado'],
};
</script>
