# Lambda

1. AWS Lambda让您可以将代码作为函数运行，而不需要配置或管理服务器。
2. 基于Lambda的应用程序（也称为无服务器应用程序）由事件触发的函数组成。
3. 通过无服务器计算，你的应用仍然运行在服务器上，但所有的服务器管理都由AWS完成。
4. 您无法登录到运行Lambda函数的计算实例，也无法自定义操作系统或语言运行时。
5. Lambda函数：
   - 由代码和任何相关的依赖关系组成。
   - 配置信息与功能相关联。
   - 您在创建函数时指定配置信息。
   - 为更新配置数据提供API。
6. 您可以指定您需要分配给Lambda函数的内存量。
7. AWS Lambda 使用与通用 EC2 实例类型相同的比例，按照您指定的内存比例分配 CPU 功率。
8. 函数可以访问：
   - AWS服务或非AWS服务。
   - 在VPC中运行的AWS服务（如RedShift、Elasticache、RDS实例）。
   - 在AWS VPC的EC2实例上运行的非AWS服务。
9. 要使您的Lambda函数能够访问私有VPC内的资源，您必须提供额外的VPC特定配置信息，包括VPC子网ID和安全组ID。
10. AWS Lambda 使用这些信息来设置弹性网络接口 (ENI)，以实现您的功能。
11. 计算资源：
    - 您可以从128MB到3008MB，以64MB的增量申请额外的内存。
    - 大于1536MB的函数要分配多个CPU线程，需要多线程或多进程代码来利用。
12. 有一个最大的执行超时：
    - 最大为15分钟（900秒），默认为3秒。
    - 你要为它运行的时间付费。
    - Lambda在超时时终止函数。
13. 代码是通过使用AWS SDK进行的API调用来调用的。
14. Lambda在执行函数时承担IAM角色。
15. 处理程序名称指的是您代码中Lambda开始执行的方法。
16. AWS Lambda的组成部分是：
    - 一个Lambda函数，由您的自定义代码和任何依赖的库组成。
    - 事件源，如SNS或自定义服务，触发你的函数并执行其逻辑。
    - 下游资源，如DynamoDB或Amazon S3 buckets，一旦你的Lambda函数被触发，它就会被调用。
    - 日志流是自定义的日志语句，允许您分析Lambda函数的执行流程和性能。
17. Lambda是一种事件驱动的计算服务，AWS Lambda会根据事件运行代码，例如S3桶或DynamoDB表中的数据变化。
18. 事件源是指AWS服务或开发者创建的应用程序，它产生的事件会触发AWS Lambda函数运行。
19. 事件源被映射到Lambda函数。
20. 除了基于流的服务(如DynamoDB、Kinesis)，事件源会维护映射配置，这些服务的配置是在Lambda端进行的，Lambda会执行轮询。
21. 支持的AWS事件源包括：
    - Amazon S3
    - Amazon DynamoDB
    - Amazon Kinesis Data Streams
    - Amazon Simple Notification Service
    - Amazon Simple Email Service
    - Amazon Simple Queue Service
    - Amazon Cognito
    - AWS CloudFormation
    - Amazon CloudWatch Logs
    - Amazon CloudWatch Events
    - AWS CodeCommit
    - Scheduled Events (powered by Amazon CloudWatch Events).
    - AWS Config
    - Amazon Alexa
    - Amazon Lex
    - Amazon API Gateway
    - AWS IoT Button
    - Amazon CloudFront
    - Amazon Kinesis Data Firehose
    - Other Event Sources: Invoking a Lambda Function On Demand
22. Lambda可以使用Amazon API网关或使用AWS SDK进行的API调用响应HTTP请求运行代码。
23. AWS Lambda支持用Node.js (JavaScript)、Python、Java（兼容Java 8）、C#（.NET Core）、Ruby、Go和PowerShell编写的代码。
24. AWS Lambda将代码存储在Amazon S3中，并在静态时对其进行加密。
25. Lambda可将并发执行函数的规模扩大到您的默认限制（1000）。
26. Lambda函数是无服务器独立的，1个事件=1个函数。
27. 功能可以触发其他功能，所以1个事件可以触发多个功能。
28. 对于非基于流的事件源，每个发布的事件都是一个工作单位，在您的账户限额内并行运行（每个事件一个Lambda函数）。
29. 对于基于流的事件源，碎片的数量表示并发的单位（每个碎片一个函数）。
30. Lambda在全球范围内工作。
31. 要启用VPC支持，您需要在单个VPC中指定一个或多个子网和一个安全组作为功能配置的一部分。
32. Lambda函数只提供对单个VPC的访问。如果指定了多个子网，它们必须都在同一个VPC中。
33. 配置为访问特定 VPC 中的资源的 Lambda 函数默认配置将无法访问 Internet。如果您需要访问外部端点，您需要在VPC中创建NAT来转发此流量，并配置您的安全组以允许此出站流量。
34. 版本管理可以用来运行不同版本的代码。
35. 每个Lambda函数都有一个唯一的亚马逊资源名（ARN），发布后不能更改。
36. 用例可分为以下几类：
    - 使用Lambda函数与AWS服务作为事件源。
    - 使用Amazon API Gateway（自定义REST API和端点）通过HTTPS按需调用Lambda函数。
    - 使用自定义应用程序（移动、Web应用程序、客户端）和AWS SDK、AWS Mobile SDK和AWS Mobile SDK for Android按需调用Lambda函数。
    - 可以通过AWS Lambda Console配置调度事件，以便按计划运行代码。

## 构建Lambda应用

1. 您可以使用AWS无服务器应用模型（AWS SAM）部署和管理您的无服务器应用。
2. AWS SAM是一个规范，规定了在AWS上表达无服务器应用的规则。本规范与 AWS CloudFormation 目前使用的语法一致，并在 AWS CloudFormation 中作为一组资源类型（称为 "无服务器资源"）得到原生支持。
3. 您可以使用 AWS CodePipeline 和 AWS CodeDeploy 自动化您的无服务器应用程序的发布流程。
4. 您可以启用您的Lambda函数，以便使用AWS X-Ray进行追踪。

## Lambda@Edge

1. Lambda@Edge允许您在全球范围内跨AWS位置运行代码，而无需配置或管理服务器，以最低的网络延迟响应终端用户。
2. Lambda@Edge让您可以运行Node.js和Python Lambda函数来定制CloudFront交付的内容，在更靠近查看者的AWS位置执行这些函数。这些函数响应 CloudFront 事件而运行，无需调配或管理服务器。您可以在以下几点使用Lambda函数更改CloudFront请求和响应。
   - 在CloudFront收到来自查看器的请求（查看器请求）后。
   - 在CloudFront将请求转发到原点（原点请求）之前。
   - 在CloudFront收到来自原点的响应（原点响应）后。
   - 在CloudFront将响应转发给浏览者（浏览者响应）之前。
3. 您只需将您的Node.js代码上传到AWS Lambda，并配置您的函数以响应Amazon CloudFront请求而触发。然后，当收到对内容的请求时，该代码就可以在AWS全球各地执行，并随着CloudFront全球请求量的增加而扩展。

## 限制

1. 内存--最低128MB，最高3008MB，以64MB递增。
2. 每次调用的短暂磁盘容量（/tmp空间）--512MB。
3. 文件描述符的数量----1024个。
4. 进程和线程数（合并）--1024。
5. 每次请求的最长执行时间--900秒。
6. 每个账户的并发执行数 - 1000（软限制）。

## 监控

1. Lambda 通过 CloudWatch 自动监控 Lambda 功能并报告指标。
2. Lambda跟踪请求数量、每个请求的延迟以及导致错误的请求数量。
3. 您可以使用 AWS Lambda Console、CloudWatch 控制台和其他 AWS 资源查看请求率和错误率。
4. X-Ray 是一项 AWS 服务，可用于检测、分析和优化 Lambda 应用程序的性能问题。
5. X-Ray从Lambda服务和组成您的应用程序的任何上游和下游服务中收集元数据。
6. Lambda 与 CloudTrail 集成，用于捕获 API 调用，并可将日志文件传送到您的 S3 桶。

## 价格

1. 请求数量。前100万免费，然后每100万0.2元。
2. 持续时间。从代码开始执行到返回或终止的时间计算。取决于分配给函数的内存量。
