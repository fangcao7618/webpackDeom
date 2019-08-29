-   webpack 打包库和组件

    webpack 除了可以用来打包应用，还可以用来打包 js 库

    ## `实现一个大整数加法库的打包`

    -   需要打包压缩版和非压缩版本
    -   支持 [AMD/CJS/ESM](https://zhuanlan.zhihu.com/p/26567790) 模块引入

        要了解 AMD/CJD/ESM/CMD
        可以看：

        -   [前端模块化标准对比 iife amd cmd cjs umd es6](https://blog.whyoop.com/2018/08/01/js-modules/)
        -   [AMD/CMD/commonjs/ESM](https://blog.csdn.net/qq_37109325/article/details/79392481)

        [modules in browsers](https://jakearchibald.com/2017/es-modules-in-browsers/)

    -   支持 ES module

        ```javascript
        import * as largeNumber from "large-number";
        largeNumber.add("999", "1");
        ```

    -   支持 CJS

        ```javascript
        const largeNumber = require("large-number");
        largeNumber.add("999", "1");
        ```

    -   支持 AMD

        ```javascript
        require(["large-number"], function(largeNumber) {
            largeNumber.add("999", "1");
        });
        ```

    -   可以直接通过 script 引入

        ```javascript
        <script src="https://unpkg.com/large-number"></script>
        <script>
            largeNumber.add("999", "1");
            window.largeNumber.add("999", "1");
        </script>
        ```

    -   如何将库暴露出去？
        ![](./document/1567069185911.jpg)
