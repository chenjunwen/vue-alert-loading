<template>
  <div id="app">
    <div class="div-btn" style="color: #333333">
      <h1 style="font-weight: bold;font-size:2rem;padding-bottom: 30px">vue-alert-loading弹框demo</h1>
      <div class="dw-btn" @click="handleClick('loading1')">显示默认弹框</div>
      <div class="dw-btn btn-success" @click="handleClick('loading2')">纵向文字颜色</div>
      <div class="dw-btn btn-primary" @click="handleClick('loading3')">纵向效果无title描述</div>
      <div class="dw-btn btn-danger" @click="handleClick('loading4')">自定义小圆点</div>
      <div class="dw-btn btn-warning" @click="handleClick('loading5')">自定义背景图层色</div>
      <div class="dw-btn btn-success" @click="handleClick('loading6')">自定义加载背景色</div>
      <div class="dw-btn btn-primary" @click="handleClick('loading7')">横向图片效果</div>
      <div class="dw-btn btn-danger" @click="handleClick('loading8')">纵向图片效果</div>
      <div class="dw-btn btn-danger" @click="handleClick('loading9')">自定义加载圆点div的高度</div>
    </div>
    <vue-alert-loading :visible="loading1" text="等待是漫长的。。。" title="请稍等"/>
    <vue-alert-loading :visible="loading2" textColor="#e799ffe8" text="等待是漫长的。。。" direction="col" title="请稍等"/>
    <vue-alert-loading :visible="loading3" :loadingDivWidth="120"  text="" direction="col" title=""/>
    <vue-alert-loading :visible="loading4" :originSize="3" originBg="#21b384" originHeight="8" originWidth="8" text="等待是漫长的。。。" direction="col" title="请稍等"/>
    <vue-alert-loading :visible="loading5"  loadingMaskBg="#8c8f96a1"/>
    <vue-alert-loading :visible="loading6" loadingBg="rgb(56, 154, 129)"/>
    <vue-alert-loading :visible="loading7" type="pic" direction="row"/>
    <vue-alert-loading :visible="loading8" type="pic" direction="col"/>
    <vue-alert-loading :visible="loading9" :originDivWidth="30" :originDivHeight="30"/>
  </div>
</template>
<style scoped>
  @import "./app.css";
  body,html{
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .div-btn{
    width: 100%;
    max-width: 560px;
    margin: 200px auto;
  }

  .div-btn div{
    margin: 10px 0;
  }
</style>
<script>
export default {
  name: 'app',
  data () {
    return {
      loading1:false,
      loading2:false,
      loading3:false,
      loading4:false,
      loading5:false,
      loading6:false,
      loading7:false,
      loading8:false,
      loading9:false
    }
  },
  methods:{
    handleClick(param){
      this[param] = true;
      setTimeout(()=>{
        this[param] = false;
      },300000);
    }
  }
}
</script>

