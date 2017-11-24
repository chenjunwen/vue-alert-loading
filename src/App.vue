<template>
  <div id="app">
    <div class="div-btn">
      <h1 style="font-weight: bold;font-size:2rem;padding-bottom: 20px">vue-alert-loading弹框demo</h1>
      <div class="dw-btn btn-success" @click="handleClick()">显示弹框</div>
    </div>
    <vue-alert-loading :visible="loading" loadingDivStyle="width:240px" text="你过得还好吗" direction="col" title="请稍等"/>
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
      loading:false
    }
  },
  methods:{
    handleClick(){
      this.loading = true;
      setTimeout(()=>{
        this.loading = false;
      },3000);
    }
  }
}
</script>

