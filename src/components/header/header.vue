<template>
<div class="head">
  <div class="content-wrap">
    <div class="avatar">
      <img :src=" seller.avatar " width="64px" height="64px" alt="">

    </div>
    <div class="content">
      <div class="title">
        <span class="brand"></span>
        <span class="name">{{ seller.name }}</span>
      </div>
      <div class="description">
        {{seller.description}}/{{seller.deliveryTime}}
      </div>
      <div v-if="seller.supports" class="supports">
        <span class="icon"></span>
        <span class="text">{{seller.supports[0].description}}</span>
      </div>
    </div>
  </div>
  <div class="bulletin-wrap"></div>
</div>
</template>

<script type="text/ecmascript-6">
export default {
  props: ['seller']
}

</script>

<style>
  .head{
    color: #fff;
    background-color: gray;
  }
  .content-wrap{
    padding: 24px 12px 18px 24px;
  }
  .avatar{
    display: inline-block;
  }
  .content{
    display: inline-block;
  }

</style>
