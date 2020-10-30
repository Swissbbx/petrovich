<template>
  <div class="priceSection">
    <div class="goldPrice">
      <div>
        По карте <br />
        клуба
      </div>
      <div v-if="isUnitAlt">
        {{ info.priceGoldAlt.toFixed(2) }}
        <span class="rouble__i black__i">
          <svg
            version="1.0"
            id="rouble__b"
            xmlns="http://www.w3.org/2000/svg"
            x="0"
            y="0"
            width="19px"
            height="19px"
            viewBox="0 0 50 50"
            enable-background="new 0 0 50 50"
            xml:space="preserve"
          >
            <use
              xmlns:xlink="http://www.w3.org/1999/xlink"
              xlink:href="#rouble_black"
            >
              <svg id="rouble_black">
                <path
                  fill="#010101"
                  d="M44.431,6.112c-1.719-2.395-4.211-4.125-7.055-4.899c-3.884-0.647-7.824-0.894-11.759-0.735H9.743v22.194H3.031v8.329h6.712v4.556H3.031v8.329h6.712v5.683h9.799v-5.634h14.698v-8.329H19.542v-4.507h6.467c3.427,0.083,6.854-0.147,10.24-0.686c1.764-0.451,3.427-1.232,4.899-2.303c1.763-1.273,3.192-2.954,4.165-4.899c1.155-2.36,1.711-4.968,1.617-7.594C47.17,12.259,46.291,8.917,44.431,6.112z M35.955,19.585c-0.757,1.1-1.835,1.938-3.087,2.401c-2.557,0.664-5.201,0.928-7.839,0.784h-5.487V8.855h4.899c2.373-0.064,4.748,0.051,7.104,0.343c1.528,0.25,2.927,1.01,3.969,2.156c1.068,1.215,1.629,2.793,1.568,4.409C37.112,17.123,36.718,18.459,35.955,19.585L35.955,19.585z"
                ></path>
              </svg>
            </use>
          </svg>
        </span>
      </div>
      <div v-else>
        {{ info.priceGold.toFixed(2) }}
        <span class="rouble__i black__i">
          <svg
            version="1.0"
            id="rouble__b"
            xmlns="http://www.w3.org/2000/svg"
            x="0"
            y="0"
            width="19px"
            height="19px"
            viewBox="0 0 50 50"
            enable-background="new 0 0 50 50"
            xml:space="preserve"
          >
            <use
              xmlns:xlink="http://www.w3.org/1999/xlink"
              xlink:href="#rouble_black"
            >
              <svg id="rouble_black">
                <path
                  fill="#010101"
                  d="M44.431,6.112c-1.719-2.395-4.211-4.125-7.055-4.899c-3.884-0.647-7.824-0.894-11.759-0.735H9.743v22.194H3.031v8.329h6.712v4.556H3.031v8.329h6.712v5.683h9.799v-5.634h14.698v-8.329H19.542v-4.507h6.467c3.427,0.083,6.854-0.147,10.24-0.686c1.764-0.451,3.427-1.232,4.899-2.303c1.763-1.273,3.192-2.954,4.165-4.899c1.155-2.36,1.711-4.968,1.617-7.594C47.17,12.259,46.291,8.917,44.431,6.112z M35.955,19.585c-0.757,1.1-1.835,1.938-3.087,2.401c-2.557,0.664-5.201,0.928-7.839,0.784h-5.487V8.855h4.899c2.373-0.064,4.748,0.051,7.104,0.343c1.528,0.25,2.927,1.01,3.969,2.156c1.068,1.215,1.629,2.793,1.568,4.409C37.112,17.123,36.718,18.459,35.955,19.585L35.955,19.585z"
                ></path>
              </svg>
            </use>
          </svg>
        </span>
      </div>
    </div>

    <div class="retailPrice">
      <span v-if="isUnitAlt">{{ info.priceRetailAlt.toFixed(2) }}</span>
      <span v-else>{{ info.priceRetail.toFixed(2) }}</span>
      <span class="rouble__i black__i">
        <svg
          version="1.0"
          id="rouble__b"
          xmlns="http://www.w3.org/2000/svg"
          x="0"
          y="0"
          width="19px"
          height="19px"
          viewBox="0 0 50 50"
          enable-background="new 0 0 50 50"
          xml:space="preserve"
        >
          <use
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xlink:href="#rouble_grey"
          >
            <svg id="rouble_grey">
              <path
                fill="#a7a7a7 "
                d="M28.109,29.658c5.173,0.578,10.357-0.979,14.355-4.312c4.172-4.748,5.151-11.509,2.499-17.246c-0.847-1.953-2.2-3.644-3.92-4.899c-1.813-1.204-3.872-1.991-6.026-2.303c-2.464-0.37-4.955-0.534-7.447-0.49H9.05v23.272H3.562v5.781H9.05v5.977H3.562v5.781H9.05v8.378h6.467v-8.133h20.088v-5.781H15.517v-6.026H28.06H28.109z M15.566,6.386h12.543c2.019-0.074,4.04,0.074,6.026,0.441c1.673,0.442,3.132,1.467,4.116,2.891c1.062,1.539,1.611,3.373,1.568,5.242c0.138,2.473-0.832,4.879-2.646,6.565c-2.601,1.812-5.76,2.645-8.917,2.352H15.517V6.386H15.566z"
              ></path>
            </svg>
          </use>
        </svg>
      </span>
    </div>

    <div class="bonusPrice">Можно купить за 231,75 балла</div>

    <div class="priceSwitch">
      <div
        :class="isUnitAlt ? 'selected' : 'notSelected'"
        @click="isUnitAlt = true"
      >
        <span> За {{ info.unitAlt }} </span>
      </div>
      <div
        :class="!isUnitAlt ? 'selected' : 'notSelected'"
        @click="isUnitAlt = false"
      >
        <span> За {{ vinitelniyPadejSinleForm }} </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PriceSection',
  props: {
    info: Object,
  },
  data() {
    return {
      isUnitAlt: true,
    }
  },
  computed: {
    vinitelniyPadejSinleForm() {
      let initialWords = ['упаковка', 'штука', 'комплект', 'метр погонный']
      let resultedWords = ['упаковку', 'штуку', 'комплект', 'метр погонный']
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
.priceSection {
  margin-top: 13px;
}

.goldPrice {
  text-align: right;
}
.goldPrice > * {
  display: inline-block;
}
.goldPrice > div:first-child {
  width: 50%;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
}
.goldPrice > div:last-child {
  width: 50%;
  font-size: 25px;
  font-weight: 700;
  color: #000;
  vertical-align: bottom;
}

.retailPrice {
  text-align: right;
  color: #a7a7a7;
  font-size: 25px;
}
.retailPrice > span:first-child {
  margin-right: 6.5px;
}

.bonusPrice {
  margin-top: 5px;
  font-size: 12px;
  line-height: 17px;
  color: #999;
  text-align: right;
}

.priceSwitch {
  margin-top: 2px;
  text-align: right;
}
.priceSwitch > div {
  display: inline-block;
  padding: 3px 5px;
  margin: 0 0 0 5px;
  font-size: 13px;
  line-height: 13px;
}
.selected {
  background: #000;
  cursor: default;
  color: #fff;
}
.notSelected > span {
  color: #707070;
  border-bottom: 1px dotted #707070;
  cursor: pointer;
}
.notSelected:hover > span {
  border-bottom: none;
}
</style>
