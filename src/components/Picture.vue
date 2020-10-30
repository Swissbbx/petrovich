<template>
  <div class="picture">
    <a href="#">
      <img
        :src="
          url.slice(0, url.lastIndexOf('.')) +
            '_220x220_1' +
            url.slice(url.lastIndexOf('.'))
        "
        alt=""
      />
    </a>
  </div>
</template>

<script>
export default {
  name: 'Picture',
  props: {
    url: String,
  },
}
</script>

<style scoped>
.picture {
  text-align: center;
}
img {
  max-width: 160px;
  max-height: 160px;
  width: 100%;
  height: auto;
}
</style>
