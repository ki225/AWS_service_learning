# pricing and support
## 免費方案
- 永遠免費
  - AWS Lambda 每月允許 100 萬個免費請求和最多達 320 萬秒的運算時間。
  - Amazon DynamoDB 每月允許 25 GB 的免費儲存。
- 12 個月免費
  - 特定數量的 Amazon S3 Standard 儲存
  - Amazon EC2 每月運算時間的閾值
  - 傳出的 Amazon CloudFront 資料量。
- 試用
  - Amazon Inspector 提供 90 天免費試用。
  - Amazon Lightsail (可讓您執行虛擬私人伺服器的服務) 在 30 天內提供 750 小時的免費使用。

## 定價
- 依照用量付費
- 預留容量，付費少
- 以量計費，用越多越便宜
- 使用 AWS Pricing Calculator 計算價格


## 定價範例
- lambda
  - 每月允許 100 萬次免費請求和多達 320 萬秒的運算時間。
  - Compute Savings Plan 
    - 在 1 年或 3 年內持續使用的承諾。
    - 預留容量時付得較少。
- ec2
  - 只需支付執行個體執行時使用的運算時間。
  - Spot 執行個體
    - 能夠承受中斷的批次處理任務
  -  Savings Plans 和預留執行個體
- s3
  - 儲存 
  - 請求和資料擷取 
  - 資料傳輸
    - 付費
      - 將資料傳入和傳出 Amazon S3 
    - 免費
      - 不同的 Amazon S3 儲存貯體之間或從 Amazon S3 傳輸資料到相同 AWS 區域內的其他服務
      - 從網際網路傳入資料到 Amazon S3 
      - 從 Amazon S3 傳出資料到 Amazon CloudFront 
      - 將資料傳出到與 Amazon S3 儲存貯體位於相同 AWS 區域的 Amazon EC2 執行個體
  - 管理和複寫
    - Amazon S3 庫存、分析和物件標記。

##  AWS Billing & Cost Management 儀表板
- 支付 AWS 帳單、監控用量、以及分析和控制成本。

## 合併帳單
- AWS Organizations 
  - AWS Organizations 的合併帳單功能，能將組織中的所有 AWS 帳戶全部集中在一張帳單上。
  - 預設帳戶數目上限為 4 個，可以增加
  - 在組織中帳戶中共用大量折扣定價、Savings Plans 和預留執行個體。
    - 合併多個帳戶時，總用量可能可以達到折扣方案門檻。

## AWS Budgets
- 建立預算來規劃服務用量、服務成本和執行個體保留。
- 每天更新三次資訊
- 在用量超過 (或預測會超過) 預算金額時設定自訂提醒。

## AWS Cost Explorer
- 視覺化、了解和管理隨著時間推進 AWS 成本和用量的工具。
- 報告
  - 預設：前五高的 AWS 服務之成本和用量
  - 自訂
- ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715482800/tk6lyKxY5HH_oG1SyiGBOw/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/qVPV0tVdd1XcwzfQ_pS6DLACY5OOiDZZb.png)

## AWS support plan
- 目的：提供最佳的工具與專業組合，獲得最佳績效，有效控管風險和成本。
- 基本支援
  - 白皮書、文件和支援社群的存取權限。
  - 詢問帳單問題和增加服務限制。
  - 存取有限的 AWS Trusted Advisor 檢查。
  - AWS 個人運作狀態儀表板工具
- 支援計劃種類
  - 開發人員支援計畫
    - 成本最低
  - 商業支援計劃
    - **AWS Trusted Advisor 檢查**
  - 企業快速通道支援計畫
    - **AWS Trusted Advisor 檢查**
    - **可與 Technical Account Manager (TAM) 聯絡**
  - 企業支援計畫
    - 成本最高
    - **AWS Trusted Advisor 檢查**
    - **可與 Technical Account Manager (TAM) 聯絡**

## Technical Account Manager (TAM)
- TAM 是您在 AWS 的主要聯絡窗口。
- TAM 提供專家工程指引、協助設計可有效整合 AWS 服務的解決方案、協助提供符合成本效益和彈性的架構，以及直接存取 AWS 計畫和廣泛的專家社群。

## AWS Marketplace
- 包含獨立軟體開發廠商數千種軟體產品的數位型錄
- 在 AWS Marketplace 尋找、測試和購買能在 AWS 上執行的軟體。 
- 提供多種類別的產品，例如基礎設施軟體、DevOps、資料產品、專業服務、商業應用程式、機器學習、工業和物聯網 (IoT)。