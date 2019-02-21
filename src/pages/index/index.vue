<template>
  <div>
    <header>
      <div class="svgDiv"></div>
      <!--<svg viewBox="0 0 100 100">
        <polygon points="112,0 85,100 1000,100 1000,0" fill="#4752a4"/>
      </svg>-->
      <div class="header-main">
        
        <div class="flex-container">
          <div class="flex-item">
            <img :src="headerImg" alt="">
          </div>
          <div class="flex-item">
            <p>缪楷</p>
            <p>Web前端开发工程师</p>
          </div>
        </div>
      </div>
      <navigator url="/pages/menu/main" class="weui-cell__ft_in-access" hover-class="weui-cell_active"></navigator>
    </header>
    <!--<div class="tasks-box">
      <div class="tasks-items">
        <span>13</span>
        <span>待办事项</span>
      </div>
      <div class="tasks-items">
         <span>16</span>
        <span>已完成</span>
      </div>
    </div>
    <div class="tasks-main">
      <h3>TODAY</h3>
    </div>-->
  </div>
</template>

<script>

export default {
  components: {
  },
  data () {
    return {
      headerImg: 'https://oss.anyitech.ltd/ws_oss_service/storage/file_reader/617401005A4690D46B5C0000',
      rightBottom: {horizontal: 'right', vertical: 'bottom'},
      list: [
        {
          open: false,
          title: 'NodeJS学习',
          main: '在云服务器创建一个进程，用NodeJS搭建Web服务器。'
        },
        {
          open: false,
          title: 'Vue+webpack学习',
          main: '完成个人网站Vue+Webpack框架搭建以及网站首页。'
        }
      ]
    }
  },

  methods: {
    changeToggle: function (e) {
      var index = e.currentTarget.dataset.index
      if (this.list[index]['open']) {
        this.list[index]['open'] = false
      } else {
        this.list[index]['open'] = true
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style lang="scss" scoped>
header{
    width: 100%;
    //height:215px;
    position: relative;
  .weui-cell__ft_in-access{
    position: absolute;
    right:25px;
    top:30px;
    &:after{
      width:10px;
      height:10px;
      border-color: #fff
    }
  }
  svg,.svgDiv{
    width:100%;
    height: 100%;
    background: #404996;
    position: absolute;
    z-index: -1;
  };
  .header-main{
    padding: 10px
  }
  .flex-container{
    display: -webkit-flex;
    display: flex;
    -webkit-align-items: center;
    align-items: center;
    padding: 10px 15px 15px 15px;
    width: 100%;
    .flex-item{
      &:first-of-type{
        -webkit-flex: 0.8;
        flex: 0.8;
        padding: 10px 0;
        >img{
          width: 90px;
          height:90px;
          //background: #fff;
          border-radius: 500px
        }
      }
      &:last-of-type{
        -webkit-flex: 2;
        flex: 2;
        >p{
          padding-left: 26px;
          color: #68d3ff;
          font-size: 16px;
          margin: 5px 0;
          &:first-of-type{
            color: #fff;
            font-size: 18px
          }
        }
      }
    }
  }
}
.tasks-box{
  display: flex;
  text-align: center;
  -webkit-align-items: center;
  align-items: center;
  .tasks-items{
    flex: 1;
    padding: 20px 0;
    background: #4dc2ff;
    color: #fff;
    &:last-of-type{
      background: #ff7fe5;
    }
    >span{
      display: block;
      line-height: 1.3;
      &:first-of-type{
        font-size: 34px
      }
      &:last-of-type{
        font-size: 14px
      }
    }
  }
}
.tasks-main{
  padding:26px 20px;
  >h3{
    font-size: 22px;
    color: #8393a3;
  }
}
.weui-cell-rot {
  background-color: #fff;
  display: flex;
  justify-content: space-between;
  font-size: 34rpx;
  width: 92%;
  padding: 0 4%;
  height: 100rpx;
  line-height: 100rpx;
  border-bottom: 1rpx solid #f1f1f1;
}
</style>
