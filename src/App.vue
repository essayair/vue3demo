<template>
  <header>
    <div class="provincepic">
    </div>
    <div class="wrapper">
      <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
      <CurrentCam msg="物产欧泰-犀小白门店监控" />
  
    </div>
  </header>

  <main>
    <CamList />
  </main>
</template>

<script>
import CurrentCam from './components/CurrentCam.vue';
import CamList from './components/CamList.vue';
import ShopPicker from './components/ShopPicker.vue'
// import ShopOption from './components/ShopOption.vue';
// import { Button  } from "ant-design-vue";
// import Button from 'ant-design-vue/lib/button';
// import 'ant-design-vue/lib/button/style';
export default {
  name: 'app',
  components: {
    CurrentCam,
    CamList,
    ShopPicker
}
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
header {
  line-height: 1.5;
}
.logo {
  display: block;
  margin: 0 auto 2rem;
}
@media (min-width: 1024px) {
  header {
    /* display: flex; */
    padding-top: 10%;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
  
    /* .logo {
      margin: 0 2rem 0 0;
    } */
  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>