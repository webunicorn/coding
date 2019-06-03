<template>
  <ul class="webtoon-frame">
    <li class="container" v-for="({ isUp, name, img, link }, idx) in webtoons" :key="idx">
      <a :href="link" target="_blank">
        <span class="badge" v-if="isUp">UP !!</span>
        <img class="img-main" :src="img">
        <span class="tit">{{ name }}</span>
      </a>
    </li>
  </ul>
</template>

<script>
export default {
  name: "webtoons",
  props: {
    webtoons: {
      type: Array,
      default: () => []
    }
  }
};
</script>

<style scoped>
.webtoon-frame {
  padding: 0 20px;
}

.container {
  position: relative;
  border-bottom: 1px solid #efefef;
  padding: 20px 0;
}

.img-main {
  width: 100%;
}
.tit {
  display: inline-block;
  margin-top: 10px;
  font-size: 18px;
  font-weight: bold;
  color: #444;
}
.badge {
  position: absolute;
  left: 0;
  top: 10px;
  background: #ff3030;
  color: #fff;
  font-weight: bold;
  padding: 8px;
}
</style>
