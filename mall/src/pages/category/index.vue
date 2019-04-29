<template>
  <div id="box">
    <div class="flexRow">
      <div>
        <img src="https://goss.veer.com/creative/vcg/veer/612/veer-134669323.jpg" alt="">
      </div>
      <div>
        <img src="https://goss.veer.com/creative/vcg/veer/612/veer-134669323.jpg" alt="">
      </div>
      <div>
        <img src="https://goss.veer.com/creative/vcg/veer/612/veer-134669323.jpg" alt="">
      </div>
      <div>
        <img src="https://goss.veer.com/creative/vcg/veer/612/veer-134669323.jpg" alt="">
      </div>
      <div>
        <img src="https://goss.veer.com/creative/vcg/veer/612/veer-134669323.jpg" alt="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    getCatList () {
      let Fly = require('flyio')
      let fly = Fly()
      fly.request({
        methods: 'post',
        url: 'https://easy-mock.com/mock/5c9edbfc8aaa6f3254a8831a/yunmayi/loginSupportDynamicPassword',
        body: {
          username: 'admin',
          password: 666666
        }
      })
        .then(res => {
          console.log(res)
        })
        .catch(err => {
          console.log(err)
        })
    }
  },
  mounted () {
    this.getCatList()
  }
}
</script>

<style scoped lang="scss">
#box {
  padding: rpx(20);
  .flexRow {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    div {
      width: 49%;
      height: rpx(270);
      margin-bottom: rpx(15);
      img {
        @include img(rpx(20));
      }
    }
  }
}
</style>
