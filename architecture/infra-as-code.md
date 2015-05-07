# Infrastructure as Code

* 程式碼可以被 trace, review, 也可以透過 `git bisect` 等指令找出出錯的 commit 並修復
* 有些服務與框架能促成這樣的工法
	* AWS 服務: CloudFormation, Elastic Beanstalk, OpsWorks, Code Deploy
	* 3<sup>rd</sup> party: Chef, Puppet, Salt, Ansible, Docker
	* DIY (透過 API 調用)
* 可以快速建出完全相同的環境，無需人工介入
	* 用於 staging & end-to-end test
	* 用於取代損壞的線上環境
	* *修復線上環境* 的時代已經過去了，現在我們產生新的替換
	* 透過這些壞了也無所謂的環境，開發者可以驗證系統確實達標：HA, Scalability, Elasticity, ...
	* 