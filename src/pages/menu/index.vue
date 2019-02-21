<template>
  <div class="page">
    <div class="page__bd">
      <div class="weui-grids">
        <block v-for="item in grids" :key="index">
          <navigator :url="item.url" class="weui-grid" hover-class="weui-grid_active">
            <image class="weui-grid__icon" :src="item.src" />
            <div class="weui-grid__label">{{item.name}}</div>
          </navigator>
        </block>
      </div>
    </div>
  </div>
</template>

<script>
// import base64 from '../../../static/images/base64'
export default {
  data () {
    return {
      grids: [
        { src: '../../../static/images/map.png', name: 'map', url: '/pages/map/main' },
        { src: '../../../static/images/banner.png', name: 'banner', url: '/pages/banner/main' }
      ]
    }
  },
  methods: {

  }
}
</script>

<style lang="scss" scoped>
page {
  margin-top: 50px;
}
</style>
