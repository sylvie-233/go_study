# gRPC

> Author: Sylvie233
>
> Date: 22/12/26
>
> Point：

## 基础介绍


```go
// 具体的service服务实现
type MyUserServer struct {}
func (us MyUserServer) GetUser(c context.Context, r *user.UserRequest) (*user.User, error) {
    id := r.GetId()
    return &user.User{
        Username: "sylvie233",
        Age:      int32(id),
    }, nil
}

func test_server() {
	rpcServer = grpc.NewServer()

	// proto生成代码(把自定义实现的myUserServer(服务实现)注册到rpc服务中)
	userService.RegisterUserServiceServer(rpcServer, MyUserServer{})
	// 开启grpc服务
	listen, err := net.Listen("tcp", ":8080")
    if err == nil {
        fmt.Println("grpc服务启动")
        rpcServer.Serve(listen)

    }
}

// 客服端连接
func test_client() {
	// 新建grpc连接
	conn, _ := grpc.Dial("127.0.0.1:8080", grpc.WithInsecure())
	// 新建grpc客户端(代码生成)
    userClient := user.NewUserServiceClient(conn)
    // grpc服务调用
    resp, _ := userClient.GetUser(context.TODO(), &user.UserRequest{Id: 233})
    fmt.Println(resp.String())
}
```












### protoc
编译工具
```
protoc:
	--go_out: 生成message字段
	--go-grpc_out: 生成grpc代码
```



### protobuf

```
syntax = "proto3";
option go_package = "./user";
package grpc_user;
  
// 定义类型对象
message XXX {
	[optional|repeated]
    string xxx = 1;
	int32|int64|double|bool|bytes|
}

// 定义服务调用
service XXX {
	[stream]
	rpc xxx (入参) returns (返回值);
}

// 导入其他proto文件
import "xxx.proto"



```

message字段可定义标识号，用于唯一区分
message可嵌套定义










## 核心内容

```
grpc:
	credentials:
		NewServerTLSFromFile(): 生成证书
	metadata:
		FromIncomingContext():
	ClientConn:
		Close():
	Server:
		Serve():
	UnaryHandler:
	UnaryInterceptor:
	UnaryServerInfo:
	Dial():
	NewServer(): 生成grpc服务
	UnaryInterceptor(): 拦截器

proto:
	Marshal(): 序列化
	Unmarshal(): 反序列化
```



### TSL
grpc配置ssl安全传输
- 私钥（key）
- 公钥
- 证书（crt）
![[Pasted image 20240502115852.png]]

私钥(key) + 证书请求(csr) => 证书/公钥(crt)


配置两个地方
- ca（证书机构）：自己生成一个证书机构
- server（服务器）：使用ca证书机构给server证书签名（最终使用的是server的私钥key和证书pem）




### Stream

rpc的请求流、响应流