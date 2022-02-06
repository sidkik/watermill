# Example Golang CQRS application

This application is using [Watermill CQRS](http://watermill.io/docs/cqrs) component.

Detailed documentation for CQRS can be found in Watermill's docs: [http://watermill.io/docs/cqrs#usage](http://watermill.io/docs/cqrs).

![CQRS Event Storming](https://threedots.tech/watermill-io/cqrs-example-storming.png)

## Running

```bash
docker-compose up
```

## Proto Generation

From this folder

```
protoc -I=inputs --go_out=. inputs/events.proto
mv github.com/ThreeDotsLabs/watermill/_examples/basic/5-cqrs-protobuf/events.pb.go events.pb.go
rm -rf github.com
```

### Protoc Install 

```
PROTOC_ZIP=protoc-3.14.0-linux-x86_64.zip
curl -OL https://github.com/protocolbuffers/protobuf/releases/download/v3.14.0/$PROTOC_ZIP
sudo unzip -o $PROTOC_ZIP -d /usr/local bin/protoc
sudo unzip -o $PROTOC_ZIP -d /usr/local 'include/*'
rm -f $PROTOC_ZIP
```

```
go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.26
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.1
```