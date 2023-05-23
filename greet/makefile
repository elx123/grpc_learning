SHELL := /bin/bash

grpc-dep:
	go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
	go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2

protoc-nomal:
	protoc ./business/greetpb/greet.proto --go-grpc_out=.

protoc-relative:
	protoc ./business/greetpb/greet.proto --go-grpc_out=. --go-grpc_opt=paths=source_relative

protoc-full:
	protoc ./business/greetpb/greet.proto --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go-grpc_opt=paths=source_relative

protoc-gateway:
	protoc ./business/greetpb/greet.proto --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go-grpc_opt=paths=source_relative --grpc-gateway_out=. --grpc-gateway_opt=paths=source_relative --grpc-gateway_opt=logtostderr=true --grpc-gateway_opt=generate_unbound_methods=true --openapiv2_out=. --openapiv2_opt=json_names_for_fields=false,logtostderr=true console.proto

buf-update:
	cd business/greetpb && buf mod update && buf generate