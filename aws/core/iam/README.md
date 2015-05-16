# IAM

AWS 作為 API 的集成，勢必需要某些機制查驗請求，達成 authenticatino 與 authorization。在 AWS 裡，負責此項功能的服務即是 <abbr title="Identity and Access Management">IAM</abbr>。除 IAM 外，<abbr tilte="Security Token Service">STS</abbr> 也作為其附加服務，提供相關功能。這篇簡介了 IAM 的幾個關鍵角色，如何與之互動，以及可能的原理。

## Identity

在 AWS IAM 裡，共有 3 種實體 (identity)，能夠被授予權限 (透過 Policy)。他們分別為 User, Group, 與 Role，功能略有差異，簡述如下：

### Group

IAM Group 的概念比較單純，用來整理 IAM User 。一個 IAM User 可以從屬與多個 Group，而這些 Group 的 IAM Policy 會被套用至 User 上。在不使用 ADFS (Active Directory Federation Service) 的前提下，用戶會以 IAM User 進行登入，並由 IAM Group 以群組的方式管理。

### User

IAM User 顧名思義，是對應至用戶的 Identity；每個人可以持有一個屬於他的帳號，使用帳號與密碼登入 AWS 網頁管理界面 (Management Console)，又或者以 Credential (Access Key 與 Secret Key) 簽署對 AWS API Endpoint 的請求。 Signing Certificate 是供 SOAP API 使用；既然現在 SOAP API 已經被 deprecate，在此便不介紹了。

若 User 有與之對應的 <abbr title="Multi-factor Authentication">MFA</abbr>，在登入網頁界面時必須帶入，否則會登入失敗。若用戶以 Credential 發請求，除非透過 Condition 設置，AWS **不查驗 MFA**。相關說明請參閱本章 <a href="aws/core/iam/README.md#More_on_STS">More on STS</a>。

除了供用戶使用以外，IAM User 有時也被用於管理供機器使用的 Credential (這不是好習慣，參照 [aws/core/iam/patterns.md](IAM 常見 Pattern))。

### Role

IAM Role 的概念

## Credential

* IAM User 的 Credential 必須自己 rotate


## IAM Policy

### Principal

### Resource

### Policy

### Condition

## <a id="More_on_STS">More on STS</a>

用戶的 MFA ARN 會與他的 IAM User ARN 相似，僅將 `user` 字樣換為 `mfa`。

### getSession

### assumeRole

## 簽署

為確保 AWS API endpoint 能處理大量併發請求，AWS 不以 session or cookie 保存連線狀態 (state)，而是針對每次 request 的 credential 進行查驗。 


