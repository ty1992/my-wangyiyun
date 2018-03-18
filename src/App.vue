<template>
  <div id="app" style="height:100%;">
    <view-box>
      <x-header class="my-header" slot="header" title="今日头条" ></x-header>
      <div>
        <scroller :lock-y="true">
          <div class="header-tab">
            <tab>
              <tab-item selected>推荐</tab-item>
              <tab-item>今日</tab-item>
              <tab-item>武汉</tab-item>
              <tab-item>忻州</tab-item>
              <tab-item>阳逻</tab-item>
              <tab-item>水泥厂</tab-item>
            </tab>
          </div>
        </scroller>
        <swiper :list="Swiper" :loop="true" :auto="true" :interval="3000" :duration="500"></swiper>
        <marquee class="marquee">
          <marquee-item v-for="i in 5" :key="i" class="align-middle">hello world {{i}}</marquee-item>
        </marquee>
      </div>
      <tabbar slot="bottom">
        <tabbar-item selected>
          <span slot="label">首页</span>
        </tabbar-item>
        <tabbar-item show-dot>
          <span slot="label">陶博</span>
        </tabbar-item>
        <tabbar-item>
          <span slot="label">陶杨</span>
        </tabbar-item>
        <tabbar-item badge="2">
          <span slot="label">我的</span>
        </tabbar-item>
      </tabbar>
    </view-box>
  </div>
</template>

<script>
  import { ViewBox,XHeader,Tabbar, TabbarItem,Tab,TabItem,Scroller,Swiper,Marquee, MarqueeItem} from 'vux'
  export default {
    components : {
      ViewBox,XHeader,Tabbar, TabbarItem,Tab,TabItem,Scroller,Swiper,Marquee, MarqueeItem
    },
    data (){
      return {Swiper : [{
        url: 'javascript:',
        img: 'https://static.vux.li/demo/1.jpg',
        title: '送你一朵fua'
      }, {
        url: 'javascript:',
        img: 'https://static.vux.li/demo/2.jpg',
        title: '送你一辆车'
      }, {
        url: 'javascript:',
        img: 'https://static.vux.li/demo/5.jpg',
        title: '送你一次旅行',
        fallbackImg: 'https://static.vux.li/demo/3.jpg'
      }]}
    }
  }
</script>
<style lang="less">
  @import '~vux/src/styles/reset.less';
  html, body {
    height: 100%;
    width: 100%;
    overflow-x: hidden;
  }
  #app{
    .header-tab{
      width:600px;
      margin-top:46px;
    }
    .marquee{
      padding:5px;
    }
    .my-header{
      position: absolute;
      top:0;left:0;width:100%;z-index:9;
    }
  }

</style>
