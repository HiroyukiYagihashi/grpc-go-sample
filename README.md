## grpc-go-sample
- Official Quick Start
  - https://grpc.io/docs/quickstart/go/
- grpcurl
  - https://github.com/fullstorydev/grpcurl

## implementation
- write proto file
- do `protoc -I helloworld/ helloworld/helloworld.proto --go_out=plugins=grpc:helloworld`
  - generate `helloworld.pb.go`
- write server code
- write client code
- DONE!

## How to use
- golang access
```
go run greeter_server/main.go
go run greeter_client/main.go
```
- grpcurl access
```
go run greeter_server/main.go
SayHello:
grpcurl -plaintext -import-path . -proto helloworld/helloworld.proto -d '{ "name": "hiroyuki" }' -rpc-header 'auth: auth value' localhost:50051 helloworld.Greeter/SayHello
```
ref: https://kiririmode.hatenablog.jp/entry/20181008/1538984412
