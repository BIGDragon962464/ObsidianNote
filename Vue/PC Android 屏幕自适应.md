#### 安装 lib-flexible
`npm install lib-flexible --save-dev`
####  引入 lib-flexible
在main.js中引入lib-flexible
```html
// px2rem 自适应
import 'lib-flexible'
```
#### 安装 postcss-pxtorem
`npm install postcss-pxtorem --save-dev`
#### 配置postcss-pxtorem
在项目根目录新建文件vue.config.js，然后如下配置：
注意脚手架不同，postcss版本也会不同，配置方法会有些许差异，不然会报错！！
vue脚手架4用的（vue-cli@4） 
vue.config.js
```javascript
// 适配不同屏幕
const autoprefixer = require('autoprefixer'); //根据浏览器适配css，自动加前缀，不用可以删除
const pxtorem = require('postcss-pxtorem');
module.exports = {
  //postcss-pxtorem
  css: {
    loaderOptions: {
      css: {},
      postcss: {
        plugins: [
          autoprefixer(),
          pxtorem({
            rootValue: 37.5,  //手机设计稿宽度为375px的
            propList: ['*'], //属性的选择器，*表示通用
            exclude: /web/i, //忽略web下的所有文件
            selectorBlackList: ['.a-'] // 过滤掉.a- 开头的class，不进行rem转换
          }),
        ]
      }
    }
  },
};
```
vue脚手架5用的（vue-cli@5）
vue.config.js
```javascript
// 适配不同屏幕
const autoprefixer = require('autoprefixer'); //根据浏览器适配css，自动加前缀，不用可以删除
const pxtorem = require('postcss-pxtorem');
module.exports = {
    //postcss-pxtorem
    css: {
        loaderOptions: {
            css: {},
            postcss: {
                postcssOptions: {
                    plugins: [
                        autoprefixer(),
                        pxtorem({
                           rootValue: 37.5,  //手机设计稿宽度为375px的
                           propList: ['*'], //属性的选择器，*表示通用
                           exclude: /web/i, //忽略web下的所有文件
                           selectorBlackList: ['.a-'] // 过滤掉.a- 开头的class，不进行rem转换
                        }),
                    ]
                }
            }
        }
    },
};
```
 如果想ios，ipad，iPod设备无效
```javascript
// 在index.html中添加如下代码
<script>
    /(pad|pod|iPad|iPod|iOS)/i.test(navigator.userAgent)&&(head=document.getElementsByTagName('head'),viewport=document.createElement('meta'),viewport.name='viewport',viewport.content='target-densitydpi=device-dpi, width=480px, user-scalable=no',head.length>0&&head[head.length-1].appendChild(viewport));
</script>
```
#### 配置pc自适应
修改flexble.js,（npm安装的位置在node_modules/lib-flexble/），建议拉出来单独引用
修改前：
```javascript
function refreshRem(){
    var width = docEl.getBoundingClientRect().width;
    if (width / dpr > 540) {
        width = 540 * dpr;
    }
    var rem = width / 10;
    docEl.style.fontSize = rem + 'px';
    flexible.rem = win.rem = rem;
}
```
 
修改后：
```javascript
function refreshRem(){
        var width = docEl.getBoundingClientRect().width;
        if (width / dpr > 770) { //大于770像素时，改变自适应策略，改成手机设计稿大小
            width = width * dpr / 5.12; 
            //520改成width 以pc上也能自适应
            // 5.12(pc设计稿除以手机，1920/350=5.12)，如果只写电脑 就不需要加
            //因为rem设置的是手机的设计稿换算的，只能在font-size上动手脚
        }
        var rem = width / 10;
        docEl.style.fontSize = rem + 'px';
        flexible.rem = win.rem = rem;
    }
```

