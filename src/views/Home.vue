<template>
  <div class="home">
      <div class="item">
          <label>默认</label>
          <FeelButton @click="click">button</FeelButton>
      </div>
      <div class="item">
          <label>禁用</label>
           <FeelButton :disabled="true">disabled</FeelButton>
      </div>
      <div class="item">
          <label>圆角</label>
          <FeelButton circle>circle</FeelButton>
      </div>
      <div class="item">
          <label>小号</label>
          <FeelButton small circle>small</FeelButton>
      </div>
      <div class="item">
          <label>大号</label>
          <FeelButton large circle>large</FeelButton>
      </div>
      <div class="item">
          <label>自定义颜色</label>
          <FeelButton small color="red" bgColor="blue">color</FeelButton>
      </div>
  </div>
</template>

<script>
// @ is an alias to /src
import FeelButton from '@/components/button.vue'

export default {
  name: 'Home',
  components: {
    FeelButton
  },
  methods:{
      click(){
          console.log("click")
      }
  }
}
</script>
<style lang="less">
    .home{
        margin: 0 auto;
        text-align: center;
    }
    .home button {
        margin: 10px;
    }
    .home label {
        display: inline;
    }
    .home .item {
        display: flex;
        align-items: center;
    }
</style>
