# Storage Gateway

1. AWS存储网关服务可以实现内部环境和AWS云之间的混合存储。
2. 它通过本地缓存频繁访问的数据来提供低延迟性能，同时将数据安全持久地存储在亚马逊云存储服务中。
3. 使用您在企业内部运行的虚拟机（VMware或Hyper-V虚拟设备）实现。
4. 提供由AWS S3和Glacier支持的本地存储资源。
5. 常用于灾难恢复准备中，将数据同步到AWS。
6. 在云计算迁移中很有用。
7. AWS存储网关支持三种存储接口：文件、卷和磁带。
8. 下表显示了不同的可用网关以及接口和用例。

   |New Name|Interface|Use Case|
   |----|----|-------|-------|
   |File Gateway|NFS, SMB|Allow on-prem or EC2 instances to store objects in S3 via NFS or SMB mount points|
   |Volume Gateway Stored Mode|iSCSI|Asynchronous replication of on-prem data to S3|
   |Volume Gateway Cached Mode|iSCSI|Primary data stored in S3 with frequently accessed data cached locally on-prem|
   |Tape Gateway|Gateway-Virtual Tape Library|iSCSI|Virtual media changer and tape library for use with existing backup software|

9. 你的每个网关都可以提供一种类型的接口。
10. 任何类型的网关设备和AWS存储之间传输的所有数据都使用SSL加密。
11. 默认情况下，AWS存储网关存储在S3中的所有数据都会在服务器端使用Amazon S3-Managed Encryption Keys (SSE-S3)进行加密。
12. 在使用文件网关时，您可以选择配置每个文件共享，以便使用SSE-KMS使用AWS KMS管理的密钥对您的对象进行加密。

## 文件网关

1. 文件网关提供了一个虚拟的预置文件服务器，使您能够将文件作为对象存储和检索到Amazon S3中。
2. 可用于预置应用，以及需要将文件存储在S3中的基于对象的工作负载的Amazon EC2驻留应用。
3. 仅用于平面文件，直接存储在S3上。
4. 文件网关提供了对Amazon S3中数据的基于SMB或NFS的访问，并提供本地缓存。
5. 文件网关支持Amazon S3 Standard、S3 Standard - Infrequent Access（S3 Standard - IA）和S3 One Zone - IA。
6. 文件网关支持客户端使用NFS v3和v4.1连接到网关。
7. 支持SMB的微软Windows客户端可以连接到文件网关。
8. 单个文件的最大大小为5TB。

## 卷网关

1. 卷网关代表了支持基于块的卷的网关家族，以前称为网关缓存和网关存储模式。
2. 块存储--基于iSCSI。
3. 缓存卷模式--整个数据集存储在S3上，现场缓存最常访问的数据。
4. 存储卷模式--整个数据集现场存储，并异步备份到S3（EBS时间点快照）。快照是增量和压缩的。
5. 每个体积网关最多可支持32个体积。
6. 在缓存模式下，每个卷最多可以达到32TB，每个网关的数据量最大为1PB（32卷，每卷32TB）。
7. 在存储模式下，每个卷最多可以达到16TB，每个网关最多可存储512TB的数据（32个卷，每个卷的大小为16TB）。

## Gateway虚拟磁带库

1. 用于与流行的备份软件进行备份。
2. 每个网关都预先配置了一个介质交换器和磁带驱动器。支持NetBackup、Backup Exec、Veeam等。
3. 当创建虚拟磁带时，您可以选择以下尺寸之一。100 GB、200 GB、400 GB、800 GB、1.5 TB 和 2.5 TB。
4. 一个磁带网关最多可拥有1500个虚拟磁带，最大总容量为1PB。
