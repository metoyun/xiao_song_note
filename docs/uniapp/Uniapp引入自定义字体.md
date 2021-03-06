
# Uniapp引入字体文件

1.  打开 [transfonter](https://transfonter.org/) 将你的字体文件生成出多种格式的字体包，以便兼容各种平台
2.  生成后下载```@font-face套件``` 
3.  解压字体套件压缩包
4.  将字体文件导入到项目下的```static```文件目录下
5.  将压缩包里的css文件复制到你的项目, 代码如下

> 建议使用Base64,更好的兼容各个平台 ,小程序平台不支持引入本地资源

<CodeSwitcher :languages="{base64:'Base64编码',file:'字体文件',}">

<template v-slot:file>
 
``` css

  //将路径改成你的字体文件目录
  @font-face {
    font-family: 'DIN Alternate';
    src: url('~@/static/fonts/DINAlternate-Bold.woff2') format('woff2'),
      url('~@/static/fonts/DINAlternate-Bold.woff') format('woff');
    font-weight: bold;
    font-style: normal;
    font-display: swap;
  }
  

  //设置一个class名使用此字体
  .DIN_Alternate_Bold {
    font-family: 'DIN Alternate' !important;
    font-style: normal;
  }

```
</template>
<template v-slot:base64>

 ``` css

//需要在transfonter转换时勾选Base64 encode
  @font-face {
    font-family: 'DIN Alternate';
    src: url('data:font/woff2;charset=utf-8;base64,·····') format('woff2'),
      url('data:font/woff2;charset=utf-8;base64,····') format('woff');
    font-weight: bold;
    font-style: normal;
    font-display: swap;
  }

  //设置一个class名使用此字体
  .DIN_Alternate_Bold {
    font-family: 'DIN Alternate' !important;
    font-style: normal;
  }

```

</template>

</CodeSwitcher>

6. 全局引入，在App.vue 引入css
``` css 
<style >
@import "static/css/index.css";
</style>
```
7. 页面内使用
``` html
<view class="DIN_Alternate_Bold" > 字体测试 </view>
```