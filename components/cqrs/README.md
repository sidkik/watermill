# Proto Generation

From this folder:

```
protoc -I=testdata --go_out=. testdata/events.proto
mv github.com/ThreeDotsLabs/watermill/components/cqrs/events.pb.go marshaler_protobuf_events_test.go
rm -rf github.com
```