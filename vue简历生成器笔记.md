#### 安装vue-cli

npm i -g vue-cli

vue init webpack . (在当前目录下)

npm install

npm run dev (开启一个静态服务器，会自动刷新)

vue可以在man.js注册一个全局组件（在初始化Vue之前），方便后面的单文件组件调用

```
Vue.component('jack',{
  complate:'<p>I am {{name}}</p>',
  data(){
    return {
      name:'Jack'
    }
  }
})
//其他单文件组件就可以使用<jack>标签而不需要通过script来引入
```

- 单文件组件一般在components文件夹下，以vue文件格式结尾，文件名首字母大写（eg：Topbar.vue)。里面的内容是标准的三段式

  ```
  <complate></complate>
  <style></style>
  <script></script
  ........如果还要引入其他子组件，在script里写
  <script>
  import Topbar from './xxx'
  export default{
    components:{Topbar} //es6的新语法，相当于('Topbar':Topbar)
  }
  </script>
  ```

- main.js里面

  ```
  import Vue from './xxx'   //要引入Vue.js
  import App from './yyy'   //引入index.html里的主组件标签

  new Vue{
    el:'#app'
    template:'<App/>' 
    components:{App}
  }
  ```

  ​