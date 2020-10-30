<template>
  <div class="priceInfo">
    <div class="availability">Наличие</div>

    <PriceSection :info="info" />

    <Buy
      :info="{
        productId: info.productId,
        unit: info.unit,
        unitAlt: info.unitAlt,
        unitFull: info.unitFull,
        unitRatioAlt: info.unitRatioAlt,
        unitRatio: info.unitRatio,
      }"
    />
  </div>
</template>

<script>
import PriceSection from './PriceSection.vue'
import Buy from './Buy.vue'

export default {
  name: 'PriceInfo',
  props: {
    info: {
      productId: String,
      priceGoldAlt: Number,
      priceRetailAlt: Number,
      priceGold: Number,
      priceRetail: Number,
      unit: String,
      unitFull: String,
      unitRatio: Number,
      unitAlt: String,
      unitRatioAlt: Number,
      unitFullAlt: String,
    },
  },
  components: {
    PriceSection,
    Buy,
  },
}
</script>

<style scoped>
.availability {
  text-align: right;
  font-size: 14px;
  line-height: 1.4;
  cursor: pointer;
  color: #093;
  text-decoration: underline dotted #093;
}
.availability:hover {
  text-decoration: none;
}
</style>
