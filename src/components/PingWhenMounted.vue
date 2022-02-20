<template>
  <div>{{ pingResponse }}</div>
</template>

<script>
export default {
  data() {
    return {
      base: "https://api.coingecko.com/api/v3",
      pingResponse: "",
    };
  },

  methods: {
    ping() {
      let path = "/ping";

      this.axios
        .get(`${this.base}${path}`)
        .then((res) => (this.pingResponse = res?.data?.gecko_says));
    },
  },

  mounted() {
    this.ping();
  },
};
</script>

<style lang="scss" scoped></style>
