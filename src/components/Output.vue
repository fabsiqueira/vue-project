<template>
  <div>
    <p>{{ numero1 * 1 + numero2 * 1 }}</p>
    <p>{{ numero1 - numero2 }}</p>
    <p>{{ numero1 * numero2 }}</p>
  </div>
</template>

<script>
export default { name: "Output", props: { numero1: Number, numero2: Number } };
</script>