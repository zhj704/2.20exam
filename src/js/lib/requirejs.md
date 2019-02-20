##### requirejs是一个javascript的模块加载器。  浏览器  ---> AMD 规范  --->异步加载

##### nodejs 服务器 ----> commonjs --->同步加载


###### requirejs 是一个js文件，直接使用script标签链接就可以

```
<script src="./require.js" async="true" defer></script>

//async ：true 设置异步加载requirejs 

//IE9 不支持async属性，需要设置defer
```

##### 使用requirejs的好处：

```
1.异步加载js模块，防止阻塞页面

2.有效的管理模块之间的依赖
```


##### requirejs的API :requriejs === require define

> require([模块1，模块2，....],function(){})   引入模块

```
第一个参数:Array   依赖的模块  即使只有一个模块也必须写成数组   不能省略 

注：1> 模块是用路径引入的，路径相对于页面所在的位置查找

    2> 模块是别名引入的，路径相对的是data-main指定的路径查找
    
    3> 配置baseUrl,baseUrl需要配置绝对路径,防止配错


第二个参数:function  回调函数 功能
```

> define(模块名,[模块一,模块二，....],function(){
    
    return 
})    定义模块


```
第一个参数：模块名  string  省略不写

第二个参数:Array   依赖的模块  即使只有一个模块也必须写成数组   可以省略

第三个参数:function  回调函数 功能

```


>require.config({})  require的配置

```
require.config({
    baseUrl:''  //配置基准路径
    paths:{     //起别名
        'jquery':'查找的路径'    
    }，
    shim:{  //不符合AMD规范
        '不符合AMD规范的模块':{
            exports:""  //导出一个
            deps:['jquery']  //设置依赖
        }
    }
})
```


> http-server  cnpm install http-server -g  起服务 


```
http-server 默认起的端口是：8080

http-server -p 端口号
```










