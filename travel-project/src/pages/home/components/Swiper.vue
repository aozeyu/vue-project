<template>
  <div class="wrapper">
    <swiper ref="mySwiper" :options="swiperOptions" v-if="showSwiper">
      <swiper-slide
        v-for="(item,index) of list" :key="index"><img
          class="swiper-img"
          :src="item.imgUrl"
          alt=""
      /></swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  props:{
    list:Array
  },
  data() {
    return {
      swiperOptions: {
        pagination: ".swiper-pagination",
        loop:true
      }
    }
  },
  computed: {
    showSwiper(){
      return this.list.length
    }
  },
};
</script>

<style lang="stylus" scoped>
.wrapper>>>.swiper-pagination-bullet-active {
  background: #fff !important;
}

.wrapper {
  width: 100%;
  height: 31.25%;
  background: #eee;

  .swiper-img {
    width: 100%;
  }
}
</style>