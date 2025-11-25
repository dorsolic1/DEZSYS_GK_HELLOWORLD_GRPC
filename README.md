# Middleware Engineering "DEZSYS_GK_HELLOWORLD_GRPC"

## Assessment

### Group size
1 Person

### Result
Protocol and delivery meeting (in English)

## Requirements – Grundlagen

### 1. Questions about the gRPC framework
Answer the questions below about the gRPC framework.

### 2. Create a simple HelloWorld application using gRPC
- Use one of the tutorials listed under “Links & Further Resources”.
- Create the **proto file** defining:
    - the gRPC service
    - its data structures
- Implement a **gRPC server** in a programming language of your choice.
- Implement a **gRPC client** in the same language.
- Document every development step in your protocol.
- Describe the most important code snippets in a few sentences.
- Document:
    - the output of the application
    - any problems that occurred

## Requirements – Erweiterte Grundlagen

### 1. Customize the service
Adjust the existing service so that a simple **DataWarehouse record**  
(see exercise MidEng 7.1) can be transferred.

### 2. Documentation
Document which parts of the program had to be adapted.

## Requirements – Vertiefung

### 1. DataWarehouse client in another language
Develop the DataWarehouse client in another programming language.

### 2. Documentation
Document the implementation of the new DataWarehouse client.


## Questions
### What is gRPC and why does it work across languages and platforms?
gRPC is a high-performance RPC framework.  
It works across languages and platforms because it uses Protocol Buffers and can generate code for multiple languages.

### Describe the RPC life cycle starting with the RPC client
1. Client calls a local stub method.
2. Request is serialized.
3. Sent over the network.
4. Server deserializes and executes method.
5. Server serializes response.
6. Client receives and deserializes response.

### Describe the workflow of Protocol Buffers
1. Define messages and services in a `.proto` file.
2. Generate code using `protoc`.
3. Serialize data for transmission.
4. Deserialize data on the receiver side.

### What are the benefits of using Protocol Buffers?
- Compact and efficient.
- Cross-language support.
- Forward/backward compatible.
- Strongly typed.

### When is the use of Protocol Buffers not recommended?
- When human-readable data is needed.
- For very simple applications.
- When schema changes frequently at runtime.

### List 3 different data types that can be used with Protocol Buffers
1. int32
2. string
3. bool


## Implementierung

Start HelloWorldServer (Java)  
`gradle clean build`  
`gradle runServer`

Start HelloWorldClient (Java)  
`gradle runClient`
  

-------------------------------- Python 

Add grpcio packages  
`pip3 install grpcio grpcio-tools`  

Compile .proto file  
`python3 -m grpc_tools.protoc -I src/main/proto  
  --python_out=src/main/resources  
  --grpc_python_out=src/main/resources  
  src/main/proto/hello.proto`  

Start HelloWorldClient (Python)  
`python3 src/main/resources/helloWorldClient.py`  

## Quellen
https://grpc.io/
https://grpc.io/docs/languages/java/quickstart/
https://yidongnan.github.io/grpc-spring-boot-starter/en/
https://blog.shiftasia.com/introduction-grpc-and-implement-with-spring-boot/
https://www.baeldung.com/grpc-introduction
https://intuting.medium.com/implement-grpc-service-using-java-gradle-7a54258b60b8

Find my HelloWorld source files here: https://elearning.tgm.ac.at/mod/resource/view.php?id=188440

Intro Video (5min): https://grpc.io/docs/what-is-grpc/introduction

Intro Video (15min): https://grpc.io/docs/what-is-grpc