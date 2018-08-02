<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
    <div class="tab">
      <router-link to="/goods">商品</router-link>
      <router-link to="/ratings">评价</router-link>
      <router-link to="/seller">商家</router-link>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
import Header from './components/header/header'
import axios from 'axios'

export default {
  data () {
    return {
      seller: {}
    }
  },
  created () {
    axios.get('http://localhost:8002').then((res) => {
      this.seller = res.data.seller
      console.log(this.seller)
    }).then((err) => {
      console.log(err)
    })
  },
  components: {
    'v-header': Header
  }
}
</script>

<style>

  .tab{
    height: 40px;
    display: flex;
    line-height:40px;
    position: relative;
  }
  .tab::after{
    content: '';
    display: block;
    border-top:1px solid rgba(7,17,27,0.1);
    width: 100%;
    position: absolute;
    left: 0;
    bottom: 0;
  }
  .tab a{
    flex: 1;
    text-align: center;
    font-size: 14px;
    display: block;
    color: rgb(77,85,93);
  }
  .tab .router-link-active{
  color: rgb(240, 20, 20);
}
</style>
