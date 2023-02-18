# Tracing using Spring Sleuth Opentelemetry with Kafka without OTLP Collector

## Jaeger Ports

The container exposes the following ports:

Port	Protocol	Component	Function
6831	UDP	agent	accept jaeger.thrift over Thrift-compact protocol (used by most SDKs)
6832	UDP	agent	accept jaeger.thrift over Thrift-binary protocol (used by Node.js SDK)
5775	UDP	agent	(deprecated) accept zipkin.thrift over compact Thrift protocol (used by legacy clients only)
5778	HTTP	agent	serve configs (sampling, etc.)
16686	HTTP	query	serve frontend
4317	HTTP	collector	accept OpenTelemetry Protocol (OTLP) over gRPC, if enabled
4318	HTTP	collector	accept OpenTelemetry Protocol (OTLP) over HTTP, if enabled
14268	HTTP	collector	accept jaeger.thrift directly from clients
14250	HTTP	collector	accept model.proto
9411	HTTP	collector	Zipkin compatible endpoint (optional)

### Manage Spans

https://docs.spring.io/spring-cloud-sleuth/docs/current-SNAPSHOT/reference/html/using.html#using-creating-and-ending-spans

### Continue Same Span

https://docs.spring.io/spring-cloud-sleuth/docs/current-SNAPSHOT/reference/html/using.html#using-continuing-spans

### Explicit Parent Span

https://docs.spring.io/spring-cloud-sleuth/docs/current-SNAPSHOT/reference/html/using.html#using-creating-spans-with-explicit-parent

### References

1. https://spring.io/blog/2022/09/16/spring-cloud-sleuth-opentelemetry-otel-1-1-0-has-been-released
2. https://betterprogramming.pub/distributed-tracing-with-opentelemetry-spring-cloud-sleuth-kafka-and-jaeger-939e35f45821
3. https://www.baeldung.com/spring-cloud-sleuth-single-application
4. https://reachmnadeem.wordpress.com/2021/02/07/distributed-tracing-with-spring-cloud-sleuth-otel-and-grafana-tempo/