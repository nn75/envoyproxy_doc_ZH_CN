### L3/L4网络过滤器

如监听器部分所述，（L3/L4）网络过滤器构成Envoy连接处理的核心。过滤器API允许将不同的过滤器组混合，并匹配到指定的监听器。有三种不同类型的网络过滤器：

- Read：Envoy从下游连接接收数据时调用Read过滤器。
- Write：当Envoy要将数据发送到下游连接时，将调用Write过滤器。
- Read/Write：当Envoy从下游连接接收数据并且要将数据发送到下游连接时，都会调用Read/Write过滤器。

网络级过滤器的API相对简单，因为最终过滤器在原始字节和少量连接事件（例如，TLS握手完成，连接本地或远程断开连接等）上操作。链路交互中的过滤器可以停止，或者随后继续迭代以进一步过滤。这可以实现更复杂的场景，例如调用速率限制服务等。Envoy已经包含了多个网络级的过滤器，这些过滤器在此体系架构概述、[配置参考](../../Configurationreference/Networkfilters.md)中都有说明。

### 返回
- [架构介绍](../Architectureoverview.md)
- [简介](../../Introduction.md)
- [首页目录](../../README.md)