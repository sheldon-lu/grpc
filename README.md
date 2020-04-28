# grpc

Golang 社区最受欢迎的微服务框架 [go-micro](https://github.com/micro/go-micro) 
整合了 gRPC 的四种数据交互模式，以及Gomicro实现grpc的demo
具体参考：
GRPC
[原文档](https://grpc.io/docs/tutorials/basic/go.html) 
[中文文档](https://doc.oschina.net/grpc)


## 目录结构

```
$GOPATH
└── grpc
    ├── simple			// 简单模式 RPC
    │   ├── client	
    │   │   └── client.go	# 客户端代码
    │   ├── proto			
    │   │   ├── user.pb.go	
    │   │   └── user.proto	# 通信的 protobuf 协议
    │   └── server
    │       └── server.go	# 服务端代码
    ├── server-side-streaming	// 服务端流式 RPC 
    ├── client-side-streaming	// 客户端流式 RPC 
    ├── bidirectional-streaming	// 客户端与服务端双向流式 RPC
    ├── grpc-demo               // grpc的官方例子
    ├── grpc-micro              // grpc在micro
    ├── go.mod
    ├── go.sum
    └── README.md
```

# grpc

The most popular microservice framework of the golang community [go micro] (https://github.com/micro/go-micro)
It integrates four data interaction modes of grpc and gomicro to realize the demo of grpc

Specific reference:
GRPC
[original file](https://grpc.io/docs/tutorials/basic/go.html)
[Chinese document](https://doc.oschina.net/grpc)

## Directory structure

```
$GOPATH
└── grpc
    ├── simple			// simple mode RPC
    │   ├── client	
    │   │   └── client.go
    │   ├── proto			
    │   │   ├── user.pb.go	
    │   │   └── user.proto
    │   └── server
    │       └── server.go
    ├── server-side-streaming	// server side streaming RPC 
    ├── client-side-streaming	// client streaming RPC 
    ├── bidirectional-streaming	// two way streaming RPC between
    ├── grpc-demo               // golang - grpc
    ├── grpc-micro              // grpc in micro
    ├── go.mod
    ├── go.sum
    └── README.md
``` 

