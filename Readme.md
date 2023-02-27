# OpenTelemetry-Example 

# Concepts
在 OpenTelemetry 中，Baggage 是跨度之间传递的上下文信息。它是一个键值存储，与跟踪中的跨度上下文一起驻留，使值可用于在该跟踪中创建的任何跨度。

例如，假设您想CustomerId在跟踪中的每个跨度上都有一个属性，这涉及多个服务；但是，CustomerId仅在一项特定服务中可用。为实现您的目标，您可以使用 OpenTelemetry Baggage 在整个系统中传播此值。

OTel Baggage 应用于您可以向第三方公开的非敏感数据。这是因为它与当前上下文一起存储在 HTTP 标头中。

Baggage - 为整条追踪连保存跨服务（跨进程）的K/V格式的用户自定义数据。Baggage 与 Attributes 类似，也是 K/V 键值对。与 Attributes 不同的是：
- 其key跟value都只能是字符串格式
- Baggage不仅当前span可见，其会随着SpanContext传递给后续所有的子span。要小心谨慎的使用Baggage - 因为在所有的span中传递这些K,V会带来不小的网络和CPU开销。

## References
[opentelemetry-go](https://opentelemetry.io/docs/instrumentation/go/getting-started/)

[链路跟踪-背景知识](https://goframe.org/pages/viewpage.action?pageId=38575612)
