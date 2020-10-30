<template>
  <div class="generalInfo">
    <div class="code">
      Код: {{ info.code.slice(info.code.search(/[1-9]/i)) }}
    </div>
    <div class="title">
      <a href="#">
        {{ info.title }}
      </a>
    </div>
    <div class="assocProducts">
      <span>Могут понадобиться: </span>
      <span
        v-for="(additionalProduct, index) in additionalProducts"
        :key="index"
      >
        <a href="#">{{ additionalProduct.trim() }}</a
        >{{ index === additionalProducts.length - 1 ? '.' : ',' }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GeneralInfo',
  props: {
    info: {
      code: String,
      title: String,
      assocProducts: String,
    },
  },
  data() {
    return {
      additionalProducts: this.info.assocProducts.split(';').filter((el) => el),
    }
  },
}
</script>

<style scoped>
.generalInfo {
  padding-left: 17px;
}

.code {
  margin-top: 2px;
  font-size: 12px;
  color: #666;
}

.title {
  margin-top: 14px;
  font-size: 16px;
  line-height: 24px;
  font-weight: 700;
}
.title a {
  text-decoration: none;
  color: #000;
  background-color: transparent;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out;
  cursor: pointer;
}
.title a:hover {
  text-decoration: underline;
}

.assocProducts {
  margin-top: 15px;
}
.assocProducts a {
  font-size: 13px;
  line-height: 16px;
  color: #666;
  text-decoration: none;
  background-color: transparent;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out;
}
.assocProducts a:hover {
  text-decoration: underline;
}
.assocProducts > span:first-child {
  font-size: 13px;
  line-height: 16px;
  color: #545454;
  font-weight: 700;
}
</style>
