# t1 start 

## 使用说明

```bash
#项目骨架
ng new my-app
#启动并打开新页面
ng serve --open
```

## 关于模块(摘自官网)

定义了名为 AppModule 的根模块，它会告诉 Angular 如何组装应用。
这里最初只声明一个 AppComponent。
当你向应用中添加更多组件时，它们也必须在这里声明
使用命令添加组件,会自动导入到 declarations 这里


NgModule的理解
为组件提供了编译的上下文环境,把相关的一些代码收集到相关的功能集中
Angular 应用就是由一组 NgModule 定义出的。 应用至少会有一个用于引导应用的根模块，通常还会有很多特性模块。

declarations（可声明对象表） —— 那些属于本 NgModule 的组件、指令、管道。
exports（导出表） —— 那些能在其它模块的组件模板中使用的可声明对象的子集
imports（导入表） —— 那些导出了本模块中的组件模板所需的类的其它模块。
providers ——
本模块向全局服务中贡献的那些服务的创建器。 这些服务能被本应用中的任何部分使用。（你也可以在组件级别指定服务提供商，这通常是首选方式。）

bootstrap —— 应用的主视图，称为根组件。它是应用中所有其它视图的宿主。只有根模块才应该设置这个 bootstrap 属性


## 添加路由

```bash
ng generate module app-routing --flat --module=app
```
添加了新模块,叫做 AppRoutingModule 

--flat 把这个文件放进了 src/app 中，而不是单独的目录中。   (貌似flat只会生成 module.ts文件)
--module=app 告诉 CLI 把它注册到 AppModule 的 imports 数组中 (默认是添加到declarations数组中的)。

 1. 添加路由(components),并添加到app.module.ts的`imports`数组  
 2. 路由组件: 定义routes,并添加到import  `RouterModule.forRoot(routes)`  
 3. 路由组件:  export数组中添加RouterModule,否则后续使用`<router-outlet></router-outlet>`等会找不到
