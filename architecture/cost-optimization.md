# 省錢

* 善用 AutoScaling 以調節服務叢集大小

	Web / API Tier 常以機器負載數據進行調節；Worker 類則監控 Message Queue Length。

* 給長時間開機的機器 (資料、監控，以及服務叢集下限）購買 Reserved Instance

* 善用 Spot Instance