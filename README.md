# 这是一个单页面项目

## 用心去感受代码的灵魂Boy ♂ Next Door

### 开门！社区送温暖!

##[开源协议之间有何异同?](https://www.zhihu.com/question/19568896)


## 制作首页App组件
1.完成Header区域，使用Mint-UI中的Header组件
2.制作底部的Tabbar区域，使用的是MUI中的Tabbar.html
3.在中间区域放置一个router-view来展示路由

## 首页轮播图

## 改造 九宫格 区域的样式

## 新闻资讯 页面 制作
1.绘制界面 使用mui  media-list.html
2.使用 vue-axios获取数据
  2.1获取到的数据根据url地址跳转的id获取方法 $route.params.id
3.渲染真实数据

## 实现 新闻资讯列表 点击跳转到新闻详情
1.吧列表中的每一项改造为 router-link,同时在跳转的时候应该提供唯一的ID标识符
2.创建新闻详情的组件页面 NewsInfo.vue
3.在 路由模块中,将新闻详情的 路由地址 和 组件对应起来

## 实现 新闻详情 的 页面布局 和数据渲染

## 单独封装一个 comment.vue 评论子组件
1.先创建一个 单独的 comment.vue 组件模板
2.在需要使用    comment 组件的 页面中，先手动 导入comment组件
3.在父组件中，使用commponents属性，将刚才导入的comment组件，注册为自己的子组件
4.将注册子组件时候的注册名称，以标签形式，在页面中引用

## 获取所有的评论数据显示到页面中
1.getComments()

## 实现点击加载更多评论的功能
1.为加载更多按钮,绑定事件，在事件中，请求 下一页数据
2.点击加载更多，让PageIndex++ , 然后使用this.getComments()方法重新获取最新一页的数据
3.为了防止 新数据 覆盖老数据的情况，我们在点击 加载更多的时候，每当获取到新数据，应当让老数据 调用 数组的concat方法，拼接上数组

## 发表评论
1.吧文本框做双向数据绑定
2.为发表按钮绑定一个事件
3.校验评论内容是否为空，如果为空，则Tost提示用户 评论内容不能为空
4.通过vue-axios 发送一个请求，吧评论内容提交给 服务器 保存
5.当发表评论OK后，重新刷新列表，以查看最新的评论
    +如果调用getComments方法 重新刷新评论列表的话，可能只能得到 最后一页的评论，前几页的评论获取不到
    +当评论成功后，在客户端，手动拼接出一个 最新的评论对象，然后调用 数组的unshift方法，吧最新的评论，追加到data 中 comments 的开头;这样，就能 完美实现刷新评论列表
  
## 改造图片分析 按钮为 路由的链接并显示对应的组件页面



## 绘制 图片列表 组件页面结构并美化样式
1.制作 顶部滑动条
2.制作 底部的图片列表

### 制作顶部滑动条
1.需要借助于 MUI 中的 tab-top-webview-main.html
2.需要把 slider 区域中的 mui-fullscreen 类去掉
3.滑动条无法正常触发滑动，通过检查官方文档 这是一个JS组件，需要被动初始化
 +导入mui.js
 +调用官方提供的 方式 去初始化：
 mui('.mui-scroll-wrapper').scroll({
	deceleration: 0.0005 //flick 减速系数，系数越大，滚动速度越慢，滚动距离越小，默认值0.0006
});
4.去除webpack严格模式报错问题
 ## https://github.com/genify/babel-plugin-transform-remove-strict-mode
5.如果滑动有警告，可以加上下面样式去掉
  + *{
    touch-action : pan-y;
  }
 