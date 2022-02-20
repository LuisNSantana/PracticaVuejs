<template>
  <div>Ciclo de vida de vue</div>
</template>

<script>
export default {
  data() {
    return {};
  },

  beforeCreate() {
    console.log("beforeCreate");
  },

  created() {
    console.log("created");
  },

  mounted() {
    console.log("mounted");
  },

  beforeMount() {
    console.log("beforeMounted");
  },

  beforeUnmount() {
    console.log("unmounted");
  },

  unmounted() {
    console.log("unmounted");
  },
};
</script>

<style scoped></style>
