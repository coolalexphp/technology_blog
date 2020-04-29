> module是一个相关Go包的集合，它是源代码更替和版本控制的单元。模块由源文件形成的go.mod文件的根目录定义，包含go.mod文件的目录也被称为模块根。moudles取代旧的的基于GOPATH方法来指定在工程中使用哪些源文件或导入包。模块路径是导入包的路径前缀，go.mod文件定义模块路径，并且列出了在项目构建过程中使用的特定版本。

1. 安装

    Go版本1.11以上不用安装

2. 使用
    
    ```
    # 创建个项目（可以不在gopath中）
    mkdir /Users/lining/go_test/heiheihei

    # 创建go.mod 
    go mod init heiheihei （go mod init 后面需要跟一个名字，我这里叫heiheihei）

    # 创建入口文件
    lining:heiheihei lining$ cat main.go 
        package main

        import (
            //我们随便拉个包
            "github.com/wonderivan/logger"
        )

        func main(){
            logger.Info("嘿嘿嘿")
        }
    
    #执行项目
    lining:heiheihei lining$ go run main.go 
    go: finding github.com/wonderivan/logger v1.0.0
    go: downloading github.com/wonderivan/logger v1.0.0
    2020-04-29 23:39:50 [INFO] [/Users/lining/go_test/heiheihei/main.go:9] 嘿嘿嘿

    # 项目中会生成 go.sum
    go.sum 是所依赖项目版本的锁定

    # 可以直接将项目移动到gopath目录 不会影响当前项目的使用

    可以开开心心的在任何地方创建项目不受gopath的限制🎉

    ```

3. 相关命令
```
download                //下载模块到本地缓存，具体可以通过命令go env查看，其中环境变量GOCACHE就是缓存的地址，如果该文件夹的内容太大，可以通过命令go clean -cache
edit                    //从工具或脚本中编辑go.mod文件
graph                   //打印模块需求图
init                    //在当前目录下初始化新的模块
tidy                    //添加缺失的模块以及移除无用的模块
verify                  //验证依赖项是否达到预期的目的
why                     //解释为什么需要包或模块
```