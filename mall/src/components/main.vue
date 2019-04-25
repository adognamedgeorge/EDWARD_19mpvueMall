<template>
  <div id="box">
    <div class="flexColumn">
      <div v-for="(item, index) in categoryList" :key="index">
        <img :src="item.url" alt="">
      </div>
    </div>
    <div class="flexRow">
      <div v-for="(item, index) of newCategory" :key="index">
        <img :src="item.url" alt="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'homeMain',
  data () {
    return {
      categoryList: [
        { url: 'https://goss.veer.com/creative/vcg/veer/612/veer-134669323.jpg' },
        { url: 'https://goss2.veer.com/creative/vcg/veer/612/veer-133071017.jpg' },
        { url: 'https://goss.veer.com/creative/vcg/veer/612/veer-147395960.jpg' }
      ],
      newCategory: [
        { url: 'https://goss4.veer.com/creative/vcg/veer/612/veer-161959036.jpg' },
        { url: 'https://goss.veer.com/creative/vcg/veer/612/veer-134669323.jpg' },
        { url: 'https://goss2.veer.com/creative/vcg/veer/612/veer-133071017.jpg' },
        { url: 'https://goss.veer.com/creative/vcg/veer/612/veer-147395960.jpg' },
        { url: 'https://goss.veer.com/creative/vcg/veer/612/veer-134669323.jpg' },
        { url: 'https://goss2.veer.com/creative/vcg/veer/612/veer-133071017.jpg' }
      ]
    }
  },
  methods: {
    getList () {
      let Fly = require('flyio')
      let fly = new Fly()
      fly.get('https://easy-mock.com/mock/5ca466b55eeed03805bf4949/edward/edward')
        .then((res) => {
          console.log(res)
        })
        .catch(err => {
          console.log(err)
        })
    }
  },
  mounted () {
    this.getList()
  }
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
