# API Gateway

1. 亚马逊API网关是与后端HTTP端点、Lambda函数或其他AWS服务集成的资源和方法的集合。
2. API Gateway是一项完全托管的服务，可以让开发人员轻松发布、维护、监控和保护任何规模的API。
3. API Gateway为开发人员提供了简单、灵活、完全管理的现收现付服务，处理为应用程序后端创建和运行健壮的API的所有方面。
4. API Gateway可以处理接受和处理多达数十万次并发API调用的所有任务。
5. API调用包括流量管理、授权和访问控制、监控和API版本管理。
6. API Gateway与Lambda一起构成了AWS无服务器基础设施中面向应用的部分。
7. 后端服务包括Amazon EC2、AWS Lambda或任何Web应用（公共或私有端点）。
8. CloudFront 被用作 API Gateway 的公共端点。支持API密钥和使用计划，用于用户识别、节流或配额管理。在后台使用CloudFront，支持自定义域和SNI。
9. 可以作为产品发布，并在AWS Marketplace上进行货币化。
10. 收藏可以分阶段部署。
11. 使用IAM角色和策略或API Gateway自定义授权器授予调用方法的权限。
12. 一个API可以提出一个证书，由后端进行认证。
13. 所有使用 Amazon API Gateway 创建的 API 都只暴露 HTTPS 端点（不支持未加密的端点）。
14. 默认情况下，API Gateway会分配一个内部域，自动使用API Gateway证书。
15. 当配置你的API在自定义域名下运行时，你可以提供自己的证书。
16. 支持的数据格式包括JSON、XML、查询字符串参数和请求头。
17. 可以通过Javascript/AJAX开启跨地域资源共享（CORS），多领域使用。
    - 可用于启用来自API域以外的域的请求。
    - 允许不同域之间共享资源。
    - 在启用CORS之前，您将启用CORS的方法（GET、PUT、POST等）必须在API Gateway API中可用。
    - 如果CORS没有启用，并且API资源收到来自其他域的请求，该请求将被阻止。
    - Enable CORS on the APIs resources using the selected methods under the API Gateway.
18. 与API网关一起使用的数据类型:
    - 任何通过HTTP发送的有效载荷（总是通过HTTPS加密）。
    - 数据格式包括JSON、XML、查询字符串参数和请求头。
    - 您可以为您的API响应声明任何内容类型，然后使用转换模板将后端响应改变为您所需的格式。
19. 您可以通过配置Amazon API Gateway缓存并指定其大小（以千兆字节为单位），为API调用添加缓存。

## Endpoints

1. API端点类型指的是API的主机名。
2. API端点类型可以是边缘优化的、区域性的或私有的，这取决于您的大部分API流量来自哪里。
3. 边缘优化端点:
   - 边缘优化的 API 端点最适合地理分布的客户端。API 请求会被路由到最近的 CloudFront 存在点 (POP)。这是 API Gateway REST API 的默认端点类型。
   - 边缘优化的API将HTTP头文件的名称大写（例如，Cookie）。
   - CloudFront 在将请求转发到您的原点之前，会按照Cookie名称的自然顺序对 HTTP Cookie 进行分类。
   - 您用于边缘优化 API 的任何自定义域名适用于所有区域。
4. 区域端点：
   - 区域性的API端点是为了同一区域的客户。
   - 当运行在EC2实例上的客户端调用同一区域的API时，或者当API要服务于少量需求较高的客户端时，区域API可以减少连接开销。
   - 对于区域性 API，您使用的任何自定义域名都是特定于部署 API 的区域。
   - 如果您在多个地区部署区域API，它可以在所有地区拥有相同的自定义域名。
   - 您可以将自定义域与 Amazon Route 53 一起使用，以执行基于延迟的路由等任务。
   - 区域API端点按原样通过所有头名。
5. 私有端点：
   - 私有 API 端点是指只能使用接口 VPC 端点从您的亚马逊虚拟私有云 (VPC) 访问的 API 端点，该接口是您在 VPC 中创建的端点网络接口 (ENI)。
   - 私有API端点按原样通过所有头名。

## 其他功能

1. API Gateway提供了一些协助创建和管理API的功能。
   - 计量 - 定义计量和限制第三方开发者访问 API 的计划。
   - 安全性--API网关提供了多种工具来授权访问API和控制服务操作访问。
   - 弹性--通过节流管理流量，使后端操作能够承受流量峰值。
   - 操作监控--API Gateway提供了一个指标仪表板来监控对服务的调用。
   - 生命周期管理--同时操作多个API版本和每个版本的多个阶段，这样在新的API版本发布后，现有的应用程序可以继续调用以前的版本。
2. API Gateway为后端API提供了强大、安全、可扩展的访问，并为您的API提供多个版本和发布阶段。
3. 您可以创建并向开发人员分发API密钥。
4. 使用AWS Sig-v4授权访问API的选项。
5. 你可以对请求进行节制和监控，以保护你的后端。
6. API Gateway允许您维护一个缓存来存储API响应。
7. iOS、Android和JavaScript的SDK生成。
8. 通过使用CloudFront降低延迟和分布式拒绝服务保护。
9. 请求/响应数据转换和API模拟。
10. 提供Swagger支持。
11. 通过基于每个HTTP方法（GET、PUT）每秒请求数的节流规则来实现弹性。
12. 节流可以在多个级别进行配置，包括全局和服务呼叫。
13. 可以创建缓存，并以千兆字节为单位指定（默认情况下不启用）。
14. 缓存是为您的API的特定阶段提供的。
15. 缓存功能包括可定制的密钥和以秒为单位的API数据生存时间(TTL)，这提高了响应时间并减少了后端服务的负载。
16. API网关可以扩展到API接收的任何级别的流量。

## 记录和监测

1. 亚马逊API网关将API调用、延迟和错误率等后端性能指标（接近实时）记录到CloudWatch。
2. 您可以通过API网关仪表板（REST API）进行监控，允许您直观地监控对服务的调用。
3. API Gateway也会对第三方开发者的使用情况进行测量，数据可以在API Gateway控制台和通过API获得。
4. 亚马逊 API Gateway 与 AWS CloudTrail 集成，可提供您的 REST API 的完整可审计历史变更。
5. 对 Amazon API Gateway APIS 进行的所有用于创建、修改、删除或部署 REST API 的 API 调用都会被记录到 CloudTrail。

## 定价

1. 使用Amazon API Gateway，您只需在使用您的API时付费。
2. 没有最低费用或前期承诺。
3. 您只需为您接收的API调用和传输出去的数据量付费。
4. 私有API没有数据传输出费用（但是，在Amazon API Gateway中使用私有API时，需要支付AWS PrivateLink费用）。
5. 亚马逊API网关还提供可选的数据缓存，按小时收费，收费标准根据您选择的缓存大小而不同。
6. API Gateway免费层包括每月一百万次API调用，最长可持续12个月。
