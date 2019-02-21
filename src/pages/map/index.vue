<template>
    <map :longitude="longitude" :latitude="latitude" :markers="markers" :covers="covers" show-location>
      <cover-view>
      经度：{{longitude}}
      </cover-view>
      <cover-view>
      纬度：{{latitude}}
      </cover-view>
      <cover-view>
      速度：{{speed}}
      </cover-view>
      <cover-view>
      精度：{{accuracy}}
      </cover-view>
    </map>
</template>

<script>
export default {
  data () {
    return {
      longitude: 116.4965075,
      latitude: 40.006103,
      speed: 0,
      accuracy: 0
    }
  },

  onLoad: function () {
    var that = this
    wx.showLoading({
      title: '定位中',
      mask: true
    })
    wx.getLocation({
      type: 'gcj02',
      altitude: true, // 高精度定位
      // 定位成功，更新定位结果
      success: function (res) {
        var latitude = res.latitude
        var longitude = res.longitude
        var speed = res.speed
        var accuracy = res.accuracy
        that.longitude = longitude
        that.latitude = latitude
        that.speed = speed
        that.accuracy = accuracy
      },
      // 定位失败回调
      fail: function () {
        wx.showToast({
          title: '定位失败',
          icon: 'none'
        })
      },

      complete: function () {
        // 隐藏定位中信息进度
        wx.hideLoading()
      }

    })
  }
}
</script>

<style>
page {
  height: 100%;
}
 
.view {
  width: 100%;
  height: 100%;
}
 
map {
  width: 100%;
  height: 100%;
  background-color: #fff;
}
</style>
