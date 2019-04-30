<template>
  <div>
    <a href="../../pages/counter/main" class="counter">去往Vuex示例页面</a>
    <div class="dSearch">
      <home-search v-on:val="val"></home-search>
    </div>

    <div class="dSlide">
      <home-slide></home-slide>
      <home-nav></home-nav>
    </div>

    <div>
      <home-main></home-main>
    </div>

    <div class="userinfo" @click="bindViewTap">
      <img class="userinfo-avatar" v-if="userInfo.avatarUrl" :src="userInfo.avatarUrl" background-size="cover" />
      <img class="userinfo-avatar" src="/static/images/user.png" background-size="cover" />

      <div class="userinfo-nickname">
        <card :text="userInfo.nickName"></card>
      </div>
    </div>

    <div class="usermotto">
      <div class="user-motto">
        <card :text="motto"></card>
      </div>
    </div>

    <form class="form-container">
      <input type="text" class="form-control" :value="motto" placeholder="v-model" />
      <input type="text" class="form-control" v-model="motto" placeholder="v-model" />
      <input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy" />
    </form>

    <a href="../../pages/counter/main" class="counter">去往Vuex示例页面</a>

    <div class="all">
        <div class="left">
        </div>
        <div class="right">
        </div>
    </div>

    <div v-show="showLeft">
      <home-left></home-left>
    </div>

    <div class="mask" v-show="showLeft" @click="hidLf"></div>
  </div>
</template>

<script>
import card from '@/components/card'
import homeSearch from '@/components/search'
import homeSlide from '@/components/slide'
import homeNav from '@/components/nav'
import homeMain from '@/components/main'
import homeLeft from '@/components/left'
export default {
  data () {
    return {
      motto: 'Hello miniprograme',
      userInfo: {
        nickName: 'mpvue',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      },
      showLeft: false
    }
  },

  components: {
    card,
    homeSearch,
    homeSlide,
    homeNav,
    homeMain,
    homeLeft
  },

  methods: {
    val (childVal) {
      this.showLeft = childVal
    },
    hidLf () {
      this.showLeft = false
      console.log(123)
    },
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    },
    goCounter () {
      // const url = '../counter/main'
      // wx.navigateTo({url})
      console.log('goCounter')
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped lang="scss">
.dSearch {
  position: fixed;
  top: rpx(50);
  left: 0;
  bottom: 0;
  right: 0;
  z-index: 9;
}
.mask {
  position: fixed;
  background-color: rgba(128, 128, 128, .5);
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 99;
}
.dSlide {
  margin-top: rpx(170);
}
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: rpx(128);
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}
.all{
  width:7.5rem;
  height:1rem;
  background-color:blue;
}
.all:after{
  display:block;
  content:'';
  clear:both;
}
.left{
  float:left;
  width:3rem;
  height:1rem;
  background-color:red;
}

.right{
  float:left;
  width:4.5rem;
  height:1rem;
  background-color:green;
}
</style>
