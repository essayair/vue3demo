<script setup>
import ShopPicker from './ShopPicker.vue';

defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <!-- <h3>
      当前监控区域：
      <a  target="_blank" rel="noopener">德清站</a> -
      <a  target="_blank" rel="noopener">北区外</a>
    </h3> -->
    <h3>
      选择门店:
      <ShopPicker />
    </h3>
  </div>
  <!--
    DeviceSerial:J90781540
    accessToken: at.9eblhnswaajutmlaac3g4vckazjc5p0r-8hfoizheid-0s67max-m5kf9egl0
    appkey:e7b3fb59624343efa492089d1f686243
    width="800"  默认尺寸
    height="480"
  -->
    <!-- src="https://open.ys7.com/ezopen/h5/iframe_se?url=ezopen://open.ys7.com/203751922/1.cloud.rec&autoplay=1&accessToken=ra.4yiwhulv9ba9eeva8r4ec8s5dyilju5c-7zoomo9n8q-13afgqk-hbedafknp&begin=20200616&end=20200616" -->
  <div>
    <iframe 
    src="https://open.ys7.com/ezopen/h5/iframe_se?url=ezopen://open.ys7.com/J90781540/1.hd.live&autoplay=1&accessToken=at.7lwyf57096xmdk6s6vxu0db1bso4yt40-58gkvyk6g7-0w2zyzz-gbm6fdrke"
    width="800" 
    height="480"
    class="ysOpenDevice" 
    allowfullscreen
    frameborder="no">
    </iframe>
  </div>
</template>


<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}
h3 {
  font-size: 1.2rem;
}
.greetings h1,
.greetings h3 {
  text-align: center;
}
@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>