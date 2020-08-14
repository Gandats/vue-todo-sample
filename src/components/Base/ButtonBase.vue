<template>
  <button @click="$emit('click')">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "ButtonBase",
};
</script>

<style scoped>
button {
  background: white;
  border-radius: 0.6rem;
}
</style>
