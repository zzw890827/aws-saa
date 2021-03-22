# AWS WAF and Shield

1. AWS WAF和AWS Shield有助于保护您的AWS资源免受Web漏洞和DDoS攻击。
2. AWS WAF是一种Web应用防火墙服务，可帮助保护您的Web应用免受可能影响应用可用性、损害安全性或消耗过多资源的常见漏洞的侵害。
3. AWS Shield 为您的 AWS 资源提供扩展的 DDoS 攻击保护。获得我们的 DDoS 响应团队的 24/7 支持和 DDoS 事件的详细可见性。

## WAF

1. AWS WAF是一个网络应用防火墙，它可以帮助保护您的网络应用，防止常见的网络漏洞，这些漏洞可能会影响应用的可用性，影响安全性，或消耗过多的资源。
2. AWS WAF允许您配置规则，根据您定义的条件允许、阻止或监控（计算）Web请求，从而帮助保护Web应用程序免受攻击。这些条件包括IP地址、HTTP头、HTTP体、URI字符串、SQL注入和跨站脚本
3. AWS WAF 通过定义可定制的网络安全规则，让您可以控制允许或阻止哪些流量进入您的网络应用。
4. 新的规则可以在几分钟内部署，让您快速响应不断变化的交通模式。
5. 当AWS服务接收到对网站的请求时，这些请求会被转发给AWS WAF，以便根据定义的规则进行检查。
6. 一旦请求满足规则中定义的条件，AWS WAF 就会指示底层服务根据您定义的操作阻止或允许该请求。
7. 使用AWS WAF，您只需为您使用的东西付费。
8. AWS WAF的定价基于您部署的规则数量和您的Web应用收到的Web请求数量。
9. 没有前期的承诺。
10. AWS WAF与Amazon CloudFront和应用负载均衡器（ALB）、服务紧密集成。
11. 当您在Amazon CloudFront上使用AWS WAF时，规则会在位于世界各地靠近最终用户的所有AWS边缘位置运行。这意味着安全不会以牺牲性能为代价。
12. 被阻止的请求在到达您的网络服务器之前就会被阻止。
13. 当您在应用负载均衡器上使用AWS WAF时，您的规则在区域内运行，并可用于保护面向互联网以及内部负载均衡器。
14. AWS WAF可以让您创建规则，根据包括IP地址、HTTP头和正文或自定义URI在内的条件过滤Web流量。这为您提供了一个额外的保护层，使您免受试图利用自定义或第三方Web应用程序中的漏洞的Web攻击。此外，AWS WAF可以轻松创建规则，阻止常见的Web漏洞，如SQL注入和跨站点脚本。
15. AWS WAF允许您创建一套集中的规则，您可以在多个网站上部署。这意味着，在有许多网站和Web应用程序的环境中，你可以创建一个单一的规则集，你可以在不同的应用程序中重复使用，而不是在你想要保护的每个应用程序上重新创建该规则。
16. AWS WAF可以完全通过API进行管理，这为组织提供了自动创建和维护规则并将其纳入开发和设计流程的能力。例如，对Web应用有详细了解的开发人员可以创建一个安全规则作为部署过程的一部分。这种将安全纳入开发流程的能力，避免了应用程序和安全团队之间复杂的交接，以确保规则保持更新。
17. AWS WAF 还可以使用 AWS CloudFormation 示例模板进行自动部署和配置，该模板允许您描述您希望为 Amazon CloudFront 交付的 Web 应用程序部署的所有安全规则。
18. AWS WAF与Amazon CloudFront集成，支持AWS以外的自定义起源--这意味着您可以保护不在AWS中托管的网站。
19. 对IPv6的支持允许AWS WAF检查来自IPv6和IPv4地址的HTTP/S请求。
20. AWS WAF提供实时指标并捕获原始请求，包括IP地址、地理位置、URI、User-Agent和Referer的详细信息。
21. AWS WAF与Amazon CloudWatch完全集成，当超过阈值或发生特定攻击时，可轻松设置自定义警报。这些信息提供了有价值的情报，可用于创建新的规则以更好地保护应用程序。

## AWS Shield

1. AWS Shield是一种受管理的分布式拒绝服务(DDoS)保护服务，可保护在AWS上运行的应用程序。
2. AWS Shield提供始终在线的检测和自动在线缓解措施，可最大限度地减少应用程序的停机时间和延迟，因此无需参与AWS支持即可从DDoS保护中获益。

### AWS Shield Standard

1. 所有AWS客户均可享受AWS Shield Standard的自动保护，无需额外收费。
2. AWS Shield Standard可以抵御最常见的、经常发生的针对网站或应用的网络和传输层DDoS攻击。
3. 当将AWS Shield Standard与Amazon CloudFront和Amazon Route 53一起使用时，您将获得全面的可用性保护，以抵御所有已知的基础设施（第3层和第4层）攻击。

### AWS Shield Advanced

1. 提供更高级别的保护，防止针对运行在Amazon Elastic Compute Cloud (EC2)、Elastic Load Balancing (ELB)、Amazon CloudFront、AWS Global Accelerator和Amazon Route 53资源上的应用程序的攻击。
2. 除了标准版的网络和传输层保护外，AWS Shield Advanced还提供了针对大型复杂DDoS攻击的额外检测和缓解措施、近乎实时的攻击可视性，以及与AWS WAF（Web应用防火墙）的集成。
3. AWS Shield Advanced还为您提供24×7访问AWS DDoS响应团队(DRT)的机会，并保护您的亚马逊弹性计算云(EC2)、弹性负载均衡(ELB)、亚马逊云端(Amazon CloudFront)、AWS全球加速器和亚马逊路由53收费中的DDoS相关峰值。
4. AWS Shield Advanced 可在全球所有 Amazon CloudFront、AWS Global Accelerator 和 Amazon Route 53 边缘位置上使用。
5. Origin服务器可以是Amazon S3、Amazon Elastic Compute Cloud (EC2)、Elastic Load Balancing (ELB)或AWS之外的自定义服务器。
6. AWS Shield Advanced 包括 DDoS 费用保护，这是一种保障，可避免因 DDoS 攻击导致受保护的 Amazon EC2、Elastic Load Balancing (ELB)、Amazon CloudFront、AWS Global Accelerator 或 Amazon Route 53 上的使用量激增而产生缩放费用。
7. 如果任何 AWS Shield Advanced 受保护资源在响应 DDoS 攻击时扩大了规模，您可以通过常规的 AWS 支持渠道申请积分。
