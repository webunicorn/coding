<template>
  <div class="container">
    <h1 class="tit">Webtoon</h1>
    <input class="input-keyword" @keyup="handleKeyword" placeholder="search...">
  </div>
</template>

<script>
export default {
  methods: {
    handleKeyword ({ target: { value } }) {
      this.$emit("onChange", value);
    }
  }
};
</script>

<style scoped>
.container {
  text-align: center;
  padding: 0 20px;
}
.tit {
  font-size: 24px;
  font-weight: bold;
  padding: 20px 0;
}
.input-keyword {
  padding: 10px;
  width: 100%;
  border: 1px solid #efefef;
  border-radius: 5px;
  font-size: 17px;
  box-sizing: border-box;
}
</style>
