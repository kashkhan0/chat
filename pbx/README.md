# Protocol Buffer and gRPC definitions

Definitions for [gRPC](https://grpc.io/) client and plugins. 

gRPC clients must implement rpc service `Node`, plugins `Plugin`. 

Generated `Go` code is included. For a sample `Python` implementation of a client see [tn-cli](../tn-cli/). 
For a partial plugin implementation see [chatbot](../chatbot/).

If you want to make changes, you have to install protobuffers tool chain and gRPC. To generate `Go` bindings add the following comment to your code and run `go generate` (your actual path to `/pbx` may be different):

```
//go:generate protoc --proto_path=../pbx --go_out=plugins=grpc:../pbx ../pbx/model.proto
```

To generate `Python` bindings:

```
python -m grpc_tools.protoc -I../pbx --python_out=. --grpc_python_out=. ../pbx/model.proto
```
 
