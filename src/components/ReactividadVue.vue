<template>
  <div>
    <el-select v-model="coin" filterable placeholder="Coins">
      <!-- El key debe ser un atributo unico, 
      puede ser un atributo del objeto, o 
      puede ser el indice del array, se recomienda 
      usar atributo del objeto -->
      <el-option
        v-for="item in coins"
        :key="item.id"
        :label="item.name"
        :value="item.id"
      >
      </el-option>
    </el-select>

    <el-button type="danger" @click="getCoinbyId">Consultar</el-button>

    <span>
      <strong :class="$style.price">{{ coinPrice }}</strong>
    </span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      coin: null,
      coinInfo: null,
      coinPrice: null,
      coins: [],
      base: "https://api.coingecko.com/api/v3",
    };
  },

  mounted() {
    this.getCoinList();
  },

  methods: {
    async getCoinList() {
      let result = await this.axios.get(`${this.base}/coins/list`);

      if (result) {
        this.coins = result.data;
      }
    },

    async getCoinbyId() {
      let result = await this.axios.get(`${this.base}/coins/${this.coin}`);

      if (result) {
        this.coinInfo = result;
        this.coinPrice = result?.data?.market_data?.current_price?.usd;
      }
    },
  },
};
</script>

<style module>
.price {
  font-size: 25;
  color: red;
}
</style>
