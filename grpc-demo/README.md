# gRpc 示例程序

## gRPC

## 简介

`gRPC` 默认使用 `protocol buffers`，这是 Google 开源的一套成熟的结构数据序列化机制（当然也可以使用其他数据格式如 `JSON`）。其客户端提供Objective-C、Java接口，服务器侧则有Java、Golang、C++等接口，从而为移动端（iOS/Android）到服务器端通讯提供了一种解决方案

## 示例代码

### protobuf

```proto
syntax = "proto3";

package echo_server;

service EchoServer
{
    rpc Echo (EchoRequest) returns (EchoResponse) {}
}

message EchoRequest
{
    string msg = 1;
}

message EchoResponse
{
    string msg = 1;
}
```

这里定义了一个服务 `EchoServer`，其中有个API `Echo`。其接受参数为`EchoRequest`类型，返回`EchoResponse`类型。这里`EchoRequest`和`EchoResponse`就是普通的PB定义。


### 服务端

这里首先定义一个server结构，然后实现 `Echo` 接口。

然后调用`grpc.NewServer()` 创建一个server `s`。

接着 `pb.RegisterGreeterServer(s, &server{})` 注册这个server `s` 到 server `s`上面 

最后将创建的`net.Listener`传给 `s.Serve()`。就可以开始监听并服务了。

## 食用指南(grpc_cli使用，linux)

**1. 生成代码**

```shell
go genernate
```

**2. 查看方法**

```bash
grpc_cli ls  localhost:12345 -l
```

![ls](https://s2.ax1x.com/2019/06/20/VjyDiT.jpg)

**3. 测试方法**

```shell
grpc_cli call localhost:12345 Echo  "msg: 'gRPC CLI'"
```

![result](https://s2.ax1x.com/2019/06/20/VjyrJU.jpg)


## 通用使用（windows、linux等）

**grpc**
```shell
protoc -I helloworld --go_out=plugins=grpc:helloworld helloworld/{name}.proto
go run server/main.go
go run client/main.go
```