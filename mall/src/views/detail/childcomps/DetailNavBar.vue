<template>
  <div>
    <nav-bar>
      <div slot="left" class="back" @click="backClick">
        <img src="~assets/img/common/back.svg" alt="加载中...">
      </div>
      <div slot="center" class="title">
        <div class="title-item" @click="titleClick(index)" :class="{active: index === currentIndex}" v-for="(item, index) in titles" :key="index">{{item}}</div>
      </div>
    </nav-bar>
  </div>
</template>

<script>
  import NavBar from 'components/common/navbar/NavBar'
  export default {
    name: "DetailNavBar",
    data() {
      return {
        titles: ["商品", "参数", "评论", "推荐"],
        currentIndex: 0
      }
    },
    components: {
      NavBar
    },
    methods: {
      titleClick(index) {
        this.currentIndex = index
      },
      backClick() {
        this.$router.back();
        // this.$router.go(-1);
      }
    }
  }
</script>

<style scoped>
  .title{
    display: flex;
  }
  .title .title-item{
    flex: 1;
  }
  .active{
    color: var(--color-high-text);
  }
  .back img{
    margin-top: 12px;
  }
</style>
