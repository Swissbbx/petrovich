<template>
  <div class="item">
    <div>
      <Picture :url="item.primaryImageUrl" />
    </div>
    <div>
      <GeneralInfo
        :info="{
          code: item.code,
          title: item.title,
          assocProducts: item.assocProducts,
        }"
      />
    </div>
    <div>
      <PriceInfo
        :info="{
          productId: item.productId,
          priceGoldAlt: item.priceGoldAlt,
          priceRetailAlt: item.priceRetailAlt,
          priceGold: item.priceGold,
          priceRetail: item.priceRetail,
          unit: item.unit,
          unitFull: item.unitFull,
          unitRatio: item.unitRatio,
          unitAlt: item.unitAlt,
          unitRatioAlt: item.unitRatioAlt,
          unitFullAlt: item.unitFullAlt,
        }"
      />
    </div>
  </div>
</template>

<script>
import Picture from './Picture.vue'
import GeneralInfo from './GeneralInfo.vue'
import PriceInfo from './PriceInfo.vue'

export default {
  name: 'Item',
  props: {
    item: Object,
  },
  components: {
    Picture,
    GeneralInfo,
    PriceInfo,
  },
}
</script>

<style scoped>
.item {
  margin: 10px 5px 0 5px;
  padding: 10px 10px 18px 10px;
  max-width: calc(1000px - 2px - 10px - 20px);
  border: solid 1px #ccc;
}
.item > div {
  display: inline-block;
  vertical-align: top;
}
.item > div:first-child {
  width: 23%;
}
.item > div:nth-child(2) {
  width: 50%;
}
.item > div:last-child {
  width: 27%;
}
</style>
