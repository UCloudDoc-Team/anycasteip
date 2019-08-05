[前往 Github](https://github.com/UCloudDocs/UCloud-document/tree/master/network/ulb)

{{indexmenu_n>9}}

# 使用限制

* 当前可绑定的资源类型为云主机、物理云主机、负载均衡。

* 宣告的入口Region：华盛顿，洛杉矶，法兰克福，东京，台北，香港，新加坡

* 可绑定资源的Region（即后端服务节点可部署的地域）：香港、新加坡、法兰克福、华盛顿、洛杉矶、伦敦、台北、曼谷、雅加达、孟买、莫斯科

* AnycastEIP的购买带宽为出口带宽，当所购买出口带宽小于50Mbps时，入口带宽等于50Mbps。当所购买出口带宽大于等于50Mbps时，入口带宽等于出口带宽。多个地域同时绑定同一个AnycastEIP时，共享该带宽值。

* 产品配额：各账号下的AnycastEIP默认配额为10个。
