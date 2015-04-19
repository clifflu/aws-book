# 帳號安全

## 本章要點

* Root Account
    * 移除所有 Credentials
    * 必須啟用 MFA，最好將 MFA 與密碼分開保管
    * 確保信箱與電話暢通
* IAM User
    * 僅授予合理且低的權限，並加入限制
        * 開發者
            * 往往需要 Admin 權限，以管理 IAM Role，需透過 IAM Policy 強制要求 MFA
            * 透過 Account Policy 控管密碼強度
        * 機器
            * 可透過 IAM Policy Condition 限制來源 IP
            * 必須將 Credential Rotation 納入考量
    * Credential 不得進入 Code Repository 或其他難以 rorate 的地方
* IAM Group
    * 考慮使用 Admin Role 取代 Admin Group
* IAM Role
    * 用以進行跨帳號授權，以及第三方委任授權
    * 善用 Credential Factory Pattern
* 落實 Infrastructure as Code，確保系統一致且可追蹤修正
