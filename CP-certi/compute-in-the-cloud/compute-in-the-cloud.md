# Compute In The CLoud
## Amazon Elastic Compute Cloud (Amazon EC2)
- 在雲端以 Amazon EC2 伺服器執行個體的形式提供安全、可調整大小的運算容量。 
## 執行個體類型
- General purpose instances / 一般用途執行個體
- Compute optimized instances / 運算最佳化執行個體
  - 適合可透過高效能處理器而受益的運算密集型應用程式
  - 適合高效能 Web 伺服器、運算密集的應用程式伺服器和專用遊戲伺服器
- Memory optimized instances / 記憶體最佳化執行個體
  - 為記憶體內處理大型資料集的工作負載提供快速效能。
  - 工作負載需要在執行應用程式之前預先載入大量資料。
- Accelerated computing instances / 加速運算執行個體
  - 使用硬體加速器或協同處理器來提高執行某些功能的效率
  - 適合圖形應用程式、遊戲串流和應用程式串流等工作負載。
- Storage optimized instances / 儲存最佳化執行個體
  - 對本機儲存體上的超大型資料集進行高序列讀取及寫入存取工作負載所設計。

## EC2 定價
- On-Demand / 隨需執行
  - 這種執行個體會持續執行，直至主動停止
  - 按照使用的運算時間付費。
- Reserved Instances / 預留執行個體
  - 可以購買為期 1 年或 3 年的標準預留和可轉換預留執行個體
  - 標準預留
    - 確認EC2 執行個體類型、大小、執行區域
  - 可轉換預留執行個體
    - 支付隨需費率
    - 需要在不同可用區域或不同執行個體類型中執行 EC2 執行個體
- EC2 Instance Savings Plans 
  - 需要對執行個體系列和區域做出 1 年期或 3 年期的每小時支出承諾
  - 不需要事先指定 EC2 執行個體類型和大小 、作業系統和租用即可獲得折扣
- Spot Instances
  - 適合啟動和結束時間較彈性或可以承受中斷的工作負載。
  - 希望在啟動和停止處理任務時，不會影響業務的整體營運
  - 提出 Spot 請求，必須有 Amazon EC2 容量可用，Spot 執行個體才能啟動。
- Dedicated Hosts 
  - 完全專供您使用且含有 Amazon EC2 執行個體容量的實體伺服器。 
  - 價格最高

## Scaling Amazon EC2
- Amazon EC2 Auto Scaling
  - 根據不斷變化的應用程式需求，自動新增或移除 Amazon EC2 執行個體。
  - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715310000/sigGosoKSxSPrsboXWgt-Q/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/UmsEzpgTK6YAnzo8_3SsQzg9Kxj3ktRuJ.png)
  - 最多只能有四個 Amazon EC2 執行個體。

## Elastic Load Balancing
- 負載平衡器會作為傳入 Auto Scaling 群組之所有 Web 流量的單一聯絡窗口
- ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715310000/sigGosoKSxSPrsboXWgt-Q/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/4Gi2s1Lf6PgngYlw_IwR_Im7rBdRH0kUD.png)


## Messaging and Queuing
- 單體式應用程式
  - 緊耦合元件的應用程式
  - 單一元件故障，其他元件也會故障
- 微型服務
  - 耦合較鬆散
  - Amazon Simple Notification Service (Amazon SNS)
    - 發布者可將訊息發布給訂閱者
    - 訂閱者可能是 Web 伺服器、電子郵件地址、AWS Lambda 函數或其他幾種選項。
  - Amazon Simple Queue Service (Amazon SQS)。
    - 應用程式會將訊息傳送到佇列中。使用者或服務會從佇列擷取訊息、處理訊息，然後從佇列中刪除訊息。
    - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715310000/sigGosoKSxSPrsboXWgt-Q/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/7P1q6EVmhadI8ktb_iymvXxrZ9rIkS4m7.jpg)

## 其他運算服務
- 無伺服器運算
  - 佈建執行個體 (虛擬伺服器) -> 上傳程式碼 -> 在應用程式執行時繼續管理執行個體。
  - 自動擴展無伺服器應用程式的彈性，透過修改耗用單位 (例如輸送量和記憶體) 來調整應用程式的容量。
  - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715310000/sigGosoKSxSPrsboXWgt-Q/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/PPzn4KCnCDP9aLAQ__tmc6AMmOWfJKKCk.png)
  - AWS Lambda
    - 程式碼如有執行，費用才會產生。
- 容器
  - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715310000/sigGosoKSxSPrsboXWgt-Q/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/i9_IJhrAbPKJHUvT_XOX7fCvLDgeaPpVS.png)
  - Amazon Elastic Container Service (Amazon ECS)
    - 支援 Docker 容器，使用 API 呼叫來啟動和停止啟用 Docker 的應用程式。
  - Amazon Elastic Kubernetes Service (Amazon EKS)
    - 執行 Kubernetes，大規模部署和管理容器化應用程式。
  - AWS Fargate
    - 容器專用的無伺服器運算引擎  
    - Amazon ECS 和 Amazon EKS 都適用。 
    - 不需要佈建或管理伺服器。
