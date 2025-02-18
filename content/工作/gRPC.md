### **Introduction to gRPC in Go**
	- gRPC (Google Remote Procedure Call) is a high-performance, open-source framework developed by Google. It uses **Protocol Buffers (Protobuf)** as its interface definition language (IDL) to define services and messages. gRPC is commonly used to build APIs that are efficient, scalable, and **language-agnostic**.
		- language-agnostic:
			- 表示使用 gRPC 建立的 API，不需要特別針對某種特定的程式語言進行開發。也就是說，無論你使用 Java、Python、Go 還是其他支援 gRPC 的語言，都可以輕鬆地開發和使用這些 API，而不需要對程式碼進行大幅修改。
	- Go has excellent support for gRPC through the `google.golang.org/grpc` library.
	- ---
- ### **Why Use gRPC?**
	- **Performance**: Lightweight and faster than REST due to binary serialization with Protobuf.
	- **Code Generation**: Automatically generates server and client code from `.proto` files.
	- **Streaming**: Supports unary, server-streaming, client-streaming, and bidirectional streaming RPCs.
	- **Language Interoperability**: Works across multiple programming languages.
	- **Type Safety**: Strongly typed messages and APIs.
	- ---
- ### **Setup**
	- **Install Required Tools**:
		- Protocol Buffers Compiler (`protoc`): [Installation Guide](https://grpc.io/docs/protoc-installation/)
		- Go Plugins for `protoc`:
		  
		  ```
		  go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
		  go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
		  ```
	- **Ensure Plugins Are in Your `PATH`**:
		- ```
		  export PATH="$PATH:$(go env GOPATH)/bin"
		  ```
	- **Install gRPC Package**:
		- ```
		  go get google.golang.org/grpc
		  go get google.golang.org/protobuf
		  ```
	- ---
- ### **Building a gRPC Service in Go**
	- #### **1. Define the Service in a `.proto` File**
		- Create a file called `example.proto`:
		  ```
		  syntax = "proto3";
		  
		  package example;
		  
		  service Greeter {
		  rpc SayHello (HelloRequest) returns (HelloReply);
		  }
		  
		  message HelloRequest {
		  string name = 1;
		  }
		  
		  message HelloReply {
		  string message = 1;
		  }
		  ```
	- #### **2. Generate Go Code from `.proto`**
		- Run the `protoc` command:
		  
		  ```
		  protoc --go_out=. --go-grpc_out=. example.proto
		  ```
		- This generates:
			- `example.pb.go`: Contains the Protobuf message types.
			- `example_grpc.pb.go`: Contains the gRPC client and server interface.
	- #### **3. Implement the Server**
		- Create `server.go`:
			- ```
			  package main
			  
			  import (
			  "context"
			  "log"
			  "net"
			  
			  pb "path/to/generated/code"
			  
			  "google.golang.org/grpc"
			  )
			  
			  // Server struct implements the GreeterServer interface
			  type Server struct {
			  pb.UnimplementedGreeterServer
			  }
			  
			  // SayHello handles the SayHello RPC
			  func (s *Server) SayHello(ctx context.Context, req *pb.HelloRequest) (*pb.HelloReply, error) {
			  log.Printf("Received: %v", req.GetName())
			  return &pb.HelloReply{Message: "Hello " + req.GetName()}, nil
			  }
			  
			  func main() {
			  listener, err := net.Listen("tcp", ":50051")
			  if err != nil {
			  log.Fatalf("Failed to listen: %v", err)
			  }
			  
			  grpcServer := grpc.NewServer()
			  pb.RegisterGreeterServer(grpcServer, &Server{})
			  
			  log.Println("Server is running on port :50051")
			  if err := grpcServer.Serve(listener); err != nil {
			  log.Fatalf("Failed to serve: %v", err)
			  }
			  }
			  ```
	- #### **4. Implement the Client**
		- Create `client.go`:
			- ```
			  package main
			  
			  import (
			  "context"
			  "log"
			  "time"
			  
			  pb "path/to/generated/code"
			  
			  "google.golang.org/grpc"
			  )
			  
			  func main() {
			  conn, err := grpc.Dial("localhost:50051", grpc.WithInsecure())
			  if err != nil {
			  log.Fatalf("Failed to connect: %v", err)
			  }
			  defer conn.Close()
			  
			  client := pb.NewGreeterClient(conn)
			  
			  ctx, cancel := context.WithTimeout(context.Background(), time.Second)
			  defer cancel()
			  
			  resp, err := client.SayHello(ctx, &pb.HelloRequest{Name: "Go Developer"})
			  if err != nil {
			  log.Fatalf("Could not greet: %v", err)
			  }
			  log.Printf("Greeting: %s", resp.GetMessage())
			  }
			  ```
	- ---
- ### **Run the Application**
	- **Start the Server**:
		- ```
		  go run server.go
		  ```
	- **Run the Client**:
		- ```
		  go run client.go
		  ```
		  
		  You should see the client send a name and the server respond with a greeting.
	- ---
- ### **Key Features**
	- **Unary RPC**: Standard request-response interaction.
	- **Server Streaming RPC**: Server sends multiple responses for a single request.
	- **Client Streaming RPC**: Client sends multiple requests for a single response.
	- **Bidirectional Streaming RPC**: Both client and server send a stream of messages.
	  
	  ---
- ### **Example: Server Streaming**
	- #### Update the  `.proto`  file:
		- ```
		  service Greeter {
		  rpc SayHello (HelloRequest) returns (stream HelloReply);
		  }
		  ```
	- #### Update the Server:
		- ```
		  func (s *Server) SayHello(req *pb.HelloRequest, stream pb.Greeter_SayHelloServer) error {
		  for i := 0; i < 5; i++ {
		  err := stream.Send(&pb.HelloReply{Message: fmt.Sprintf("Hello %s - %d", req.GetName(), i+1)})
		  if err != nil {
		  	return err
		  }
		  time.Sleep(1 * time.Second)
		  }
		  return nil
		  }
		  ```
	- #### Update the Client:
		- ```
		  stream, err := client.SayHello(ctx, &pb.HelloRequest{Name: "Go Developer"})
		  if err != nil {
		  log.Fatalf("Error calling SayHello: %v", err)
		  }
		  
		  for {
		  reply, err := stream.Recv()
		  if err == io.EOF {
		  break
		  }
		  if err != nil {
		  log.Fatalf("Error receiving stream: %v", err)
		  }
		  log.Printf("Stream message: %s", reply.GetMessage())
		  }
		  ```
	- ---
- ### **Next Steps**
	- **Secure with TLS**:
		- Use `grpc.WithTransportCredentials` to enable secure communication.
	- **Interceptors**:
		- Add middleware for logging, authentication, or metrics.
	- **Load Balancing**:
		- Integrate gRPC with service discovery for distributed systems.
	- **Testing**:
		- Use Go’s `testing` package or gRPC mock services for unit tests.
-
- Would you like an example with one of these advanced topics? 😊