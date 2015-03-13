# zeptoModule
zepto.js加入touch模块fx模块自定义打包构建（基于sea.js）
zepto.js 是移动端的轻量级框架，但是官网的zepto.min.js 是没有加入touch.js 和fx.js 等其他模块的，如何将zepto模块与其他模块进行打包构建呢
##
  官网下载的默认构建包里居然不含移动设备专用的touch组件，这是脑袋被门挤了的节奏吗？要知道，在移动设备上使用click事件会有几百毫秒的延迟呢！
  所以只有自己build了。以windows为例：  
  1、从github上down一份下来（https://github.com/madrobby/zepto），把目录直接丢到x盘。  
  2、安装nodejs环境以及npm包管理器（够折腾一段时间了xD..）。  
  3、运行，打开CMD命令行，用cd命令切换到x盘的zepto目录下。  
  4、编辑目录下的make文件，找到第42行，就是modules = (env['MODULES'] || 'zepto detect event ...').split(' ')这么一行。引号里以空格分隔的就是将要打包的模块名，加入touch，保存。（当然，可以根据自己需要增减模块，核心模块zepto别删掉了就行）  
  5、回到命令行，输入npm install回车安装。安装好，再输入npm run-script dist回车，开始打包构建。  
  6、如果没有报错的话，就ok了。到dist目录下可以看到生成的三个文件：原始文件zepto.js，压缩后的zepto.min.js，gzip后的zepto.min.gz。生产环境使用zepto.min.js就行了。  
##

##
 构建后的文件在dist 文件夹下的zepto.js，但是因为是基于sea.js 的我们需要为其添加define 头部并且把module.exports 放在文件的最末尾  
 所以我自己在dist 下的zeptoModule.js 自己封装了一个zeptoModule.js  
 这个供我以后自己回顾
##

我的博文也进行了记录：[博文](http://www.w3cfuns.com/blog-5434745-5404318.html)
