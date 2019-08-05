
[前往 Github](https://github.com/UCloudDocs/UCloud-document/tree/master/network/ulb)


{{indexmenu_n>5}}

# 技术架构

AnycastEIP之基础设施

如图，UCloud全球节点，底层利用专线实现互联。每个接入点的架构如图：

公网路由器分为流量。公网流量通过UCloud Virtual Edge Router送到机房内部。UVER是基于DPDK开发的网关模块，用于收集所有EIP的路由，并将流量封装后给到下一跳。

WBR为边界路由器，负责外网流量的引入，安全也会对镜像流量  WER为边缘路由器，用于接收清洗后的流量。

从逻辑上看，UCloud的全球网络由三张网组成，一张是WBR组成的IBN网络，一张是WER组成的WER网络，一张LBN网络。其中IBN用于机房出口的容灾调度。WBN网络用于UCloud内部的公网互访。LBN则是UCloud 高速通道的承载者。

首先我们来看IBN网络。当一个机房出口出现问题后，所有的宣告直接切换到靠近的界定啊， 并通过IBN专线实现传输。

•IBN网络：机房出口级别的调度容灾

•WBN网络：UCloud之间的公网互访加速

•LBN网络：跨Region的VPC互通

IBN网络：机房的出口容灾

WBN网络，用来实现UCloud内部EIP之间的加速。海外的EIP之间互通也可以走这条专线，这样真正实现了UCloud骨干互联网这个概念。如右图所示，如果海外单个机房的ISP运营商出口全断，则可以依赖IBN网络实现出口的切换，保证机房的出口安全。

WBN网络：UCloud的内部公网加速

•如右图所示：正常的公网访问，将通过WER/WBR路径直接上公网。而不同Region之间的UCloud 公网IP的互访，则直接通过WBN网络互联。从而保证UCloud内部公网IP之间互访的质量。



