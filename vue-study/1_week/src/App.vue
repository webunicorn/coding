<template>
  <div>
    <Header @onChange="handleKeyword"/>
    <Webtoons :webtoons="filteredWebtoons"/>
  </div>
</template>

<script>
import "./assets/css/reset.css";
import Header from "./components/Header";
import Webtoons from "./components/Webtoons";
export default {
  components: {
    Header,
    Webtoons
  },
  computed: {
    filteredWebtoons () {
      if (!this.keyword) {
        return this.webtoons;
      }
      return this.webtoons.filter(
        ({ name }) => name.indexOf(this.keyword) > -1
      );
      // return this.keyword
      //   ? this.webtoons.filter(({ name }) => name.indexOf(this.keyword) > -1)
      //   : this.webtoons;
    }
  },
  data () {
    // state
    return {
      keyword: "",
      webtoons: [
        {
          name: "햄스터와 그녀",
          link: "http://webtoon.daum.net/webtoon/view/hamsterandher",
          img:
            "http://t1.daumcdn.net/webtoon/op/478cdf37f585607982ffa9e35b432e8503be8a54",
          isUp: false
        },
        {
          name: "프롬 스타",
          link: "http://webtoon.daum.net/webtoon/view/fromstar",
          img:
            "http://t1.daumcdn.net/webtoon/op/a7fb953d722c1130bfc18440f7e3ce448ece57a1",
          isUp: false
        },
        {
          name: "위대한 로맨스",
          link: "http://webtoon.daum.net/webtoon/view/greatromance",
          img:
            "http://t1.daumcdn.net/webtoon/op/a816281cb4df5c50a20ac386fd6e496643d0f085",
          isUp: true
        },
        {
          name: "빛나는 손을",
          link: "http://webtoon.daum.net/webtoon/view/Hand",
          img: "http://t1.daumcdn.net/cartoon/5913FCAC0234C50001",
          isUp: false
        }
      ]
    };
  },
  methods: {
    handleKeyword (keyword) {
      console.log("keyword", keyword);
      this.keyword = keyword;
    }
  }
};
</script>

<style>
#app {
  max-width: 720px;
  margin: 0 auto;
}
</style>