# vue-alert-loading

> Vue 自定义弹窗加载组件

## [效果演示](http://chenjunwen.github.io/vue-alert-loading)


## 安装

    npm install vue-alert-loading --save
    
## 简单使用

    <template>
        <div style="margin:0 auto;">
            <button @click="handleClick">显示默认弹窗</button>
            <vue-alert-loading :visible="visible"/>
        </div>
    </template>
    
    <script>
        import Vue from 'vue';
        import VueAlertLoading from 'vue-alert-loading';
        Vue.use(VueAlertLoading);
        
        exprot default{
            data:{
              visible:false
            },
            methods:{
                handleClick(){
                    this.visible = true;
                    setTimeout(()=>{
                        this.visible = false;
                    },3000);
                }
             }
        }
    </script>
    
## 选项

  | 参数          |  说明             | 类型      |  可选值  | 默认值|
  | :----------   |  :-----------    | :-----    | :----  | :----
  | visible       |  是否显示加载框    | Boolean   |   —    | false
  | title         |  标题             | string    |   —    | 请稍等!
  | titleColor    |  标题颜色         | string    |   —    | —
  | text          |  显示文本         | string    |   —    | —
  | textColor     |  文本颜色         | string    |   —    | —
  | direction     |  显示方向         | string    | row/col| col
  |loadingDivWidth|  加载div的宽度    | Number   |   —    | 260
  | originSize    |  小圆点的个数     | Number   |   —    | 6
  | originWidth   |  小圆点的宽度     | Number   |   —    | 6
  | originHeight  |  小圆点的高度     | Number   |   —    | 6
  | originBg      |  小圆点的背景色   | string   |   —    | —
  |originDivHeight|  小圆点父div高度  | Number   |   —    | 40
  | originDivWidth | 小圆点父div宽度  | Number   |   —    | 40
  | type          |  加载框类型       | string   |pic/origin| origin
  | loadingBg     |  加载框背景色     | string   |   —    | —
  | loadingMaskBg |  背景图层颜色     | string   |   —    | —
  
  



## 运行源码
``` bash
# 克隆项目
git clone https://github.com/chenjunwen/vue-alert-loading.git

# 进入项目目录
cd vue-alert-loading

# 安装所需模块
npm install

# 启动项目，默认访问地址 localhost:8080
npm run dev

# 打包发布
npm run build
```
