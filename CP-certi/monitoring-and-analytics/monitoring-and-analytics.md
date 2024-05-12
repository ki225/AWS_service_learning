# monitoring and analytics
## Amazon CloudWatch
- 介紹
  - 網路服務
  - 使用 [metrics](https://docs.aws.amazon.com/zh_tw/AmazonCloudWatch/latest/monitoring/working_with_metrics.html) 來表示資源的資料節點
  - 監控和管理執行應用程式所用資源的各種指標。
  - AWS 傳送 metrics 給 CloudWatch，CloudWatch 再自動使用 metrics 建立圖(也就是儀表板上可以看到的)
- 建立警示
  - 指標值超過或低於預先定義的閾值時自動執行動作。 

## AWS CloudTrail
- 追蹤整個 AWS 基礎設施的使用者活動和 API 請求
  - 帳戶 API call 完整紀錄
- 篩選日誌以協助進行操作分析和疑難排解
- CloudTrail Insights
  - 讓 CloudTrail 自動偵測 AWS 帳戶中不尋常的 API 活動。 

## AWS Trusted Advisor
- 檢查環境
- 根據 AWS 最佳實務提供即時建議。
  - 成本最佳化 optimization
    - 未使用或閒置資源的檢查，資源可以消除以節省成本
  - 效能 performance
    - 提供如何利用佈建輸送量的建議，協助改善服務的效能。
    - e.g. 對高使用率 EC2 執行個體的檢查
  - 安全性 security
    - 檢閱許可和識別要啟用哪些 AWS 安全功能的檢查
  - 容錯能力 fault tolerance
    - 有助於改善應用程式可用性和備援的檢查。
  - 服務配額 service limits
- AWS Trusted Advisor dashboard(儀表板)
  - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715482800/tk6lyKxY5HH_oG1SyiGBOw/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/57DFI8UuqARakxhv_y7m_A5IYU52xvXJw.jpg)
  - 綠色勾號表示已偵測到沒問題的項目數量。
  - 黃色三角形表示建議的調查數量。
  - 紅色圓圈表示建議的動作數量。

> [!NOTE]
> Amazon GuardDuty 這項服務用於為您的 AWS 環境和資源提供智慧威脅偵測。它透過持續監控 AWS 環境中的網路活動和帳戶行為來識別威脅。
