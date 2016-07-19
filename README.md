ngularJS提供的$window 服务
 
在传统的JavaScript中“Window”默认在任何地方是全局可用的，但是由于window是全局变量同时也给我们带来了很多问题，但是在AngularJS中
我们必须声明“$window”这个服务因为它覆盖了早已经存在的“window”变量，而且当我们测试系统的时候不会带来任何问题
，在使用window这个服务和它的属性时我们必须先声明它；
我将要创建一个简单的运用帮助我们更好的理解这个服务
第一步：
首先你需要下载Angular.min.js 这个文件放在你的运用中，你可以到官网上下载，或则
点击[AngularJS](http://www.c-sharpcorner.com/downloads/762/angularjs.aspx "Title")
新建一个文件index.js,在头部引入刚刚下载的js文件
```
<head >
    <title></title>
    <script src="angular.min.js"></script>
</head>
```
第二步：
首先在<HTML>标签中声明属性ng-app，否者程序将不会正常运行；
接下来我创建一个JavaScript函数
```
 <script>
        function func($scope, $window) {
            $scope.greet = ‘TimLiu’;
            $scope.greetFunc = function (greet) {
                $window.alert(greet);
            };
        }
    </script>
```
这个函数中使用了$scope和$window，我们通过$scope主键初始化变量的值和定义将要使用的函数，
在这里吧“TimLiu” 赋值给变量greet，这个变量的值可以在运行的时候被改变。
同时我们创建一个函数greetFunc，在这个函数中使用了$window的属性$window,这个属性将要以跳窗的形式
显示greet变量的值。
 接下来我们开始完成视图模板的部分


第三步
```
<body>
    <form id="form1" runat="server">
        <div ng-app>
            <div ng-controller="x">
                <input type="text" ng-model="greet" />
                <input type="button" ng-click="greetFunc(greet)" value="Greetings"/>
            </div>
        </div>
    </form>
</body>
```
在视图模板中我们把Div和函数func绑定，在这个div中包含一个标签和一个按钮。
标签和按钮互相绑定通过ng-model,按钮通过ng-click和函数greetFunc绑定，
现在如果点击这个按钮，会跳窗展现出greet变量的默认值，但是如果我们改变输入框的
内容，跳窗的内容也会改变。

现在开始运行这个项目
1、在浏览器中看这个项目
2、点击greetings跳窗
3、修改输入框的值然后跳窗

整个项目源代码以及angularjs在我的github账号上










