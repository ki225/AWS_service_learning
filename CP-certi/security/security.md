# security
## AWS 共同責任模型
- AWS 和客戶共同維護服務的安全
  - AWS
    - 軟體：運算、儲存、資料庫、網路
    - 硬體：區域、可用區域、節點
  - 客戶
    - 客戶資料
    - 平台、應用程式、身分與存取管理 (IAM)
    - 作業系統，以及網路和防火牆組態
    - 用戶端資料加密、伺服器端資料加密和網路流量保護

## 使用者許可與存取權限
### AWS Identity and Access Management (IAM)
- AWS account root user
  - 第一次建立 AWS 帳戶時，首先要使用名為根使用者(opens in a new tab)的身分。  
  - 請勿將根使用者用於日常工作。
  - 只有當需要執行僅限根使用者進行的有限工作時，才能使用根使用者。   
  - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715360400/gDsLZg-tazoJD5huJteLlg/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/2wSzmM-PTsmSJHoC_GXj7XwE4jMxezGDC.png)
- IAM user
  - 代表使用此實體與 AWS 服務互動的人員或應用程式。包含一組名稱和登入資料。
  - 建議為每個需要存取 AWS 的人員建立個別的 IAM 使用者。
- IAM policies
  - 能允許或拒絕 AWS 服務和資源許可的文件。
  - 自訂使用者存取資源的層級。
- IAM group
  - IAM 使用者的集合。
  - 將 IAM 政策指派給群組時，群組中的所有使用者都會獲得政策指定的許可。
  - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715360400/gDsLZg-tazoJD5huJteLlg/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/rgLEVfGCKld7b33U_iKvKZn3aq2i3ch1l.png)
- IAM role
  - 一種身份，有暫時取得存取權。
  - 當某人擔任 IAM 角色時，他們會放棄先前角色中擁有的所有許可，並取得新角色的許可。 

## 多重因素認證 / Multi-factor authentication (MFA)
- 帳號+密碼+其他驗證因素
  - e.g. 除了帳密，系統會提示使用者從其 AWS MFA 裝置輸入身份驗證回應。此裝置可以是硬體安全金鑰、硬體裝置或裝置 (例如智慧型手機) 上的 MFA 應用程式。
- 要額外啟動

## AWS Organizations
- 集中整合和管理多個 AWS 帳戶。
- 建立組織時，會自動建立根目錄，這是組織中所有帳戶的父容器。 
- 可以使用服務控制政策 (SCP)集中控制組織中的帳戶許可。
  - SCP 讓使用者限制每個帳戶中使用者和角色可以存取的 AWS 服務、資源和個別 API 動作。
  - 將 SCP 套用至組織根目錄、個別成員帳戶或 OU。SCP 會影響帳戶內所有的 IAM 使用者、群組和角色，包括 AWS 帳戶根使用者
  - 將 IAM 政策套用至 IAM 使用者、群組或角色。**無法將 IAM 政策套用至 AWS 帳戶根使用者。**

### 組織單位
- 將帳戶分組為組織單位 (OU)，輕鬆管理具有類似業務或安全需求的帳戶。
- 更輕鬆地分隔具有特定安全需求的工作負載或應用程式。
- 將政策附加到 OU，OU 中的所有帳戶會自動繼承政策中指定的許可，以阻止對不符合法規要求的所有其他 AWS 服務的存取。
- ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715360400/gDsLZg-tazoJD5huJteLlg/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/7lt6Imq0nPTKgSpj_RdUO42fD-crguQYB.png)
  - 在設計組織時，您必須考量每個部門的業務、安全和法規需求。您可以使用這些資訊，來決定要將哪些部門整合在 OU 中。
  - 人力資源部門和法律部門必須存取相同的 AWS 服務和資源，因此您可以將這些服務和資源一起放在 OU 中。將它們放入 OU 可讓您連接適用於人力資源部門和法律部門 AWS 帳戶的政策。