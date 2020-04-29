govendor安装与使用

1. 安装
```
go get -u -v github.com/kardianos/govendor
```

2. 使用
```
进入项目目录
cd /Users/lining/go/src/govendor_test

初始化govendor管理工具 创建vendor目录
govendor init

将项目中使用的包加载到项目中（如果本地GOPATH没有依赖包，先go get相应的依赖包）
govendor add +external 简写 govendor add +e
```

2.1 说明
```
govendor只是用来管理项目的依赖包，如果GOPATH中本身没有项目的依赖包，则需要通过go get先下载到GOPATH中，再通过govendor add +external拷贝到vendor目录中。
```

2.2 常用命令

|名称|用途|
|:-|:-:|
|init|初始化 vendor 目录|
|add|添加包到 vendor 目录，如 govendor add +external 添加所有外部包|
|update|从 $GOPATH 更新依赖包到 vendor 目录|
|remove|从 vendor 管理中删除依赖|
|status|列出所有缺失、过期和修改过的包|
|⭐️|待更新~|