<template>
  <div v-if="visible" :class="'cpt-loading-mask animated fadeInNoTransform '+direction"
       :style="{background: loadingMaskBg, 'z-index': 1000001, position: 'fixed'}">
    <div class="div-loading" :style="{width:loadingDivWidth+'px', background: loadingBg}">
      <p class="loading-title txt-textOneRow" :style="{color: titleColor}">{{title}}</p>

      <div v-if="type!=='pic'" class="loading origin" :style="{ height: originDivHeight+'px', width: originDivWidth +'px'}">
        <div class="div-loadingOrigin" v-for="n in originSize">
          <span :style="{'margin-top': '-10px','margin-left': '-10px', width: originWidth+'px', height: originHeight+'px', background:originBg}"></span>
        </div>
      </div>

      <div class="loading pic" :style="{ height: originDivHeight+'px', width: originDivHeight +'px'}" v-else>
          <img src="http://www.daiwei.org/index/images/logo/dw.png"  alt="loading" >
      </div>
      <p class="loading-discription txt-textOneRow" :style="{color: textColor}">{{text}}</p></div>
  </div>
</template>

<style scoped>
  @import "./css/loading.css";
  @import "./css/animate.css";
</style>

<script>
  export default {
    name:'VueAlertLoading',
    props:{
      // 标题
      title: {
        type: String,
        default: '请稍等!'
      },
      // 标题颜色
      titleColor:{
        type: String,
        default: 'rgba(255, 255, 255, 0.7)'
      },
      // loading的描述
      text: {
        type: String,
        default: ''
      },
      // 描述文本颜色
      textColor:{
        type: String,
        default: 'rgba(255,255,255,0.7)'
      },
      // 方向，col纵向   row 横向
      direction:{
        type: String,
        default: 'col'
      },
      // 是否显示
      visible:Boolean,
      // 中间加载div的样式
      loadingDivWidth: {
        type: Number,
        default: 260
      },
      // 圆点的个数
      originSize:{
        type: Number,
        default: 6
      },
      // 小圆点的宽度
      originWidth:{
        type: Number,
        default: 6
      },
      // 小圆点的高度
      originHeight:{
        type: Number,
        default: 6
      },
      // 小圆点的背景色
      originBg:{
        type:String,
        default:'rgb(254, 254, 254)'
      },
      // loadingDiv的宽度
      originDivWidth:{
        type: Number,
        default: 40
      },
      // loadingDiv的宽度
      originDivHeight:{
        type: Number,
        default: 40
      },
      //pic：图片   origin：圆点
      type:{
        type: String,
        default: 'origin'
      },
      // 中间的背景色
      loadingBg:{
        type:String,
        default:'rgba(0, 0, 0, 0.6)'
      },

      // 背景遮罩层颜色
      loadingMaskBg:{
        type:String,
        default:'rgba(0, 0, 0, 0.2)'
      }
    },
    data() {
      return {

      }
    }
  }
</script>
