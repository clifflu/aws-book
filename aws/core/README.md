# AWS 核心服務

在 AWS 所提供的服務當中，有幾項居於樞紐地位；要嘛通盤管理其他服務，又或被用於建構其他服務。在此選出五項核心服務簡單介紹，以熟悉 AWS 與雲端運算的精神，也為理解其他高階服務鋪路。這些服務有：

* [IAM](aws/core/iam/README.md) 

	管理調用 AWS API 的授權，屬於資源層級的權限控管。
* [S3](aws/core/s3/README.md)
 
	AWS 內的 Durable Storage，並提供 HA。
* [EC2](aws/core/ec2/README.md)

	虛擬機，包含 CPU 與 RAM；某些機型帶有 instance storage，並且 EC2 機器規格 (instance type) 直接影響其上網卡 (ENI, Elastic Network Interface) 的效能。 
* [EBS](aws/core/ebs/README.md)

	持久 (persistent, non-volatile) 磁碟，能掛載至 EC2 上操作。
* [VPC](aws/core/vpc/README.md)

	管理虛擬網路與網段，用以提升安全性，並管理 VPC 間的通信。 
