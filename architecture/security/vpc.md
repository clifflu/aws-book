# 網路安全

## 要項

* 使用 VPC
* 以 Security Group 代表 Instance Role，簡化機器間的連線授權管理
* Network ACL 可用於網路層黑名單，並防止 route table 設定錯誤造成非預期的端口開放
* VPC Peering 雖然能延伸 Private Network，但減低單一服務複雜度，透過 Internet 對其他 microservice 提供服務才是長治久安之道。
