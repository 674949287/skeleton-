# skeleton-

//首页骨架屏效果		--解决白屏现象
1.安装骨架屏
指令：npm install vue-skeleton-webpack-plugin -D

2.新建一个Skeleton.vue，放骨架屏的图片

3.在src下新建一个entry-skeleton.js，引入Skeleton模板
   import Vue from 'vue'
   import Skeleton from './Skeleton'
   export default new Vue({
     components:{
       Skeleton
     },
     template:'<Skeleton />'
   })


4.在build下得环境引入插件 dev.conf.js

   const SkeletonWebpackPlugin = require('vue-skeleton-webpack-plugin');
   function resolve (dir) {
    return path.join(__dirname, '..', dir)
   }

   在plugins下增加插件内容
	new SkeletonWebpackPlugin({
	   webpackConfig:{
	      entry:{
		app:resolve('./src/entry-skeleton.js')
	      }
	   }
	})

5.通过npm run dev即可看到骨架屏效果

