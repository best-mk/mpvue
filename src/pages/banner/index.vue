<template>
  <div>
    <swiper class='swiperClass' :autoplay="false" :indicator-color="indicatorColor" :indicator-active-color="indicatorActiveColor" :indicator-dots="autoplay"  :interval="interval" :duration="duration" :previous-margin="previousMargin" :next-margin="nextMargin" :circular="autoplay" @change="bindchange" style='height: 500px'>
      <div v-for="item in imgUrls" :key="index">
        <swiper-item>
          <image :src="item" :class="swiperIndex === index?'slide-image active':'slide-image quiet'" mode='aspectFill'>
          </image>
        </swiper-item>
      </div>
    </swiper>
  </div>
</template>

<script>
// import base64 from '../../../static/images/base64'
export default {
  data () {
    return {
      autoplay: true,
      indicatorColor: '#a39f99',
      indicatorActiveColor: '#f49641',
      interval: 2000,
      duration: 1000,
      previousMargin: '30px',
      nextMargin: '30px',
      imgUrls: [
        'https://oss.airiskeys.com/ws_oss_service/storage/file_reader/617401003E1E4D44925B0000',
        'https://oss.airiskeys.com/ws_oss_service/storage/file_reader/617401003E1E6044925B0000',
        'https://oss.airiskeys.com/ws_oss_service/storage/file_reader/617401003E1E6D44925B0000',
        'https://oss.airiskeys.com/ws_oss_service/storage/file_reader/617401003E1E7144925B0000'
      ],
      swiperIndex: 0 // 这里不写第一次启动展示的时候会有问题
    }
  },
  methods: {
    bindchange (e) {
      this.swiperIndex = e.mp.detail.current
    },
    swiperActive (index) {
      if (this.swiperIndex === index) {
        return 'slide-image active'
      } else {
        return 'slide-image quiet'
      }
    },
    styleActive () {
      return 'height: 500px'
    }
  }
}
</script>
<style lang="scss" scoped>
.swiperClass {
  margin: 0;
  margin-top: 10px;
}
.slide-image {
  width: 100%;
  height: 90%;
  border-radius: 10px;
  position: relative;
}
image.active {
  transform: none;
  transition: all 0.2s ease-in 0s;
}  
image.quiet {
  transform: scale(0.8333333);
  transition: all 0.2s ease-in 0s;
}
</style>
