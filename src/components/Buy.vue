<template>
  <div class="buy">
    <div class="tooltip">
      <div class="infoIcon"></div>
      <div class="text">
        Продаётся {{ tvoritelniyPadejPluralForm }}: <br />
        {{ info.unitRatio }} {{ info.unit }} =
        {{ (info.unitRatio / info.unitRatioAlt).toFixed(2) }} {{ info.unitAlt }}
      </div>
    </div>

    <div class="checkout">
      <div class="stepper">
        <input
          class="product__count stepper-input"
          type="text"
          value="1"
          v-model="amount"
        />
        <span class="stepper-arrow up" @click="amount++"></span>
        <span
          class="stepper-arrow down"
          @click="amount > 0 ? amount-- : amount"
        ></span>
      </div>

      <button class="cart" :data-product-id="info.productId">
        <svg class="ic ic_cart">
          <use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#cart">
            <svg id="cart" fill="currentColor">
              <path
                d="m14.571 16.381c.571 0 .952.381.952.952 0 .571-.381.952-.952.952-.571 0-.952-.381-.952-.952 0-.571.476-.952.952-.952m0-.952c-1.048 0-1.905.857-1.905 1.905 0 1.048.857 1.905 1.905 1.905 1.048 0 1.905-.857 1.905-1.905 0-1.048-.857-1.905-1.905-1.905"
              ></path>
              <path
                d="m7.905 16.381c.571 0 .952.381.952.952 0 .571-.381.952-.952.952-.571 0-.952-.381-.952-.952 0-.571.476-.952.952-.952m0-.952c-1.048 0-1.905.857-1.905 1.905 0 1.048.857 1.905 1.905 1.905 1.048 0 1.905-.857 1.905-1.905 0-1.048-.857-1.905-1.905-1.905"
              ></path>
              <path
                d="m16.476 14.476h-10.857l-.095-.381c0-.095-1.429-9.714-1.905-11.524-.381-1.524-3.333-1.429-3.333-1.429v-.952c.095 0 3.714-.286 4.286 2.19.381 1.714 1.619 9.333 1.81 11.143h10.1v.952"
              ></path>
              <path d="m4.095 3.048h15.238v.952h-15.238z"></path>
              <path d="m5.05 10.667h12.381v.952h-12.381z"></path>
              <path
                d="m16.476 11.619h.952l1.905-8.571h-.952l-1.905 8.571"
              ></path>
            </svg>
          </use>
        </svg>
        <span>В КОРЗИНУ</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Buy',
  props: {
    info: {
      productId: String,
      unit: String,
      unitFull: String,
      unitAlt: String,
      unitRatio: Number,
      unitRatioAlt: Number,
    },
  },
  data() {
    return {
      amount: 1,
    }
  },
  computed: {
    tvoritelniyPadejPluralForm() {
      let initialWords = ['упаковка', 'штука', 'комплект', 'метр погонный']
      let resultedWords = [
        'упаковками',
        'штуками',
        'комплектами',
        'метрами погонными',
      ]
      return initialWords.findIndex((el) => el === this.info.unitFull) > -1
        ? resultedWords[
            initialWords.findIndex((el) => el === this.info.unitFull)
          ]
        : 'неизвестно'
    },
  },
}
</script>

<style scoped>
.buy {
  margin-top: 10px;
  position: relative;
  height: 100px;
}
.tooltip {
  position: absolute;
  right: 0;
  width: 85%;
  height: 40px;
  background: #fff;
  border: 1px solid #ccc;
}
.tooltip::before,
.tooltip::after {
  content: '';
  position: absolute;
  bottom: -7px;
  border-top: 8px solid;
  display: block;
  width: 0;
  height: 0;
}
.tooltip::before {
  margin-bottom: -1px;
  border-color: #ccc;
  color: #ccc;
  left: 13px;
  border-left: 8px solid transparent !important;
  border-right: 8px solid transparent !important;
}
.tooltip::after {
  border-color: #fff !important;
  left: 14px;
  border-left: 7px solid transparent !important;
  border-right: 7px solid transparent !important;
}
.tooltip > * {
  display: inline-block;
}
.infoIcon {
  position: absolute;
  display: inline-block;
  vertical-align: top;
  width: 15px;
  height: 15px;
  /* margin: 8px 10px 0 0; */
  background: url(../assets/unit--i.png) 50% no-repeat;
  background-size: cover;
  top: 50%;
  left: 18px;
  transform: translate(-50%, -50%);
}
.text {
  position: absolute;
  left: 40px;
  top: 5px;
  font-size: 13px;
  line-height: 15px;
}

.checkout {
  position: absolute;
  top: 53px;
  right: 0;
  width: 86%;
}
.stepper {
  margin: 0 0 10px;
  overflow: hidden;
  position: absolute;
  top: 0;
  line-height: 37px;
  height: 40px;
  width: 67px;
  border: 1px solid #ccc;
}
.stepper .stepper-input {
  border: none;
  color: #333;
  font-size: 13px;
  line-height: 1.2;
  text-align: center;
  margin: 0;
  overflow: hidden;
  padding: 12px 0 10px;
  width: 40px;
  z-index: 49;
  -moz-appearance: textfield;
}
.stepper .stepper-arrow {
  background: #fff url(../assets/jquery.fs.stepper-arrows.png) no-repeat;
  border: 1px solid #ccc;
  cursor: pointer;
  display: block;
  height: 50%;
  position: absolute;
  right: 0;
  text-indent: -99999px;
  width: 25px;
  z-index: 50;
}
.stepper-arrow:hover {
  background-color: #666;
}
.stepper-arrow.up {
  background-position: -28px 0;
  border-bottom: none;
  border-top: none;
  border-right: none;
  top: 0;
}
.stepper-arrow.down {
  background-position: -28px -20px;
  border-bottom: none;
  border-right: none;
  bottom: 0;
}

.checkout > button {
  position: absolute;
  right: 0;
  height: 42px;
  width: 65%;
  background-color: #f90;
  color: #fff;
  border: transparent;
  outline: none;
}
.checkout svg {
  position: absolute;
  left: 10px;
  top: 10px;
  width: 20px;
  height: 20px;
}
.checkout > button > span {
  position: absolute;
  right: 25px;
  top: 14px;
}
.checkout > button:hover {
  background-color: #333;
}
</style>
