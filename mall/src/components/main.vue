<template>
  <div id="box">
    <div class="flexColumn">
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
    </div>
    <div class="flexRow">
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
      <div>
        <img src="/static/images/cat.png" alt="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'homeMain'
}
</script>

<style scoped lang="scss">
#box {
  padding: rpx(40) rpx(20) 0;
  .flexColumn {
    div {
      height: rpx(300);
      margin-bottom: rpx(20);
      img {
        @include img(rpx(20));
      }
    }
    div:last-child {
      height: rpx(190);
    }
  }
  .flexRow {
    background-color: yellow;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    div {
      width: 49%;
      height: rpx(270);
      margin-bottom: rpx(15);
      img {
        @include img(rpx(15));
      }
    }
  }
}
</style>
