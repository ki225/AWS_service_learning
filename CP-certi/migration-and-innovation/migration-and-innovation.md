# migration and innovation
## AWS Cloud Adoption Framework (AWS CAF)
- 六個核心觀點
  - 業務能力
    - 業務
      - 確保 IT 符合業務需求，讓 IT 投資可連結至關鍵業務成果
      - 從業務和 IT 策略有所區隔的模型轉變為整合 IT 策略的業務模型。
    - 人員
      - 評估組織結構和角色、新的技能和程序需求
      - 幫助人力資源 (HR) 員工更新組織程序和員工技能，使其具備雲端能力，幫助他們的團隊準備好採用雲端。
    - 管控
      - 如何更新必要的員工技能和程序，以確保雲端中的業務治理。管理和衡量雲端投資，以評估業務成果。
      - 辨識並實作 IT 治理的最佳實務，並以科技支援業務流程。
  - 技術能力
    - 平台
      - 雲端上實作新解決方案，以及將內部部署工作負載遷移至雲端的原則和模式。
    - 安全
      - 確保組織符合可見性、可稽核性、控制和敏捷性的安全目標。
      - 識別不合規的領域
    - 營運
      - 定義每天、每季和每年的業務執行方式。
      - 著重於營運和恢復 IT 工作負載，以滿足業務利益關係人的需求。
> [!NOTE]
> 基本上涉及「許可」的服務都和「安全有關」。
## migration strategy 遷移策略
> [!NOTE]
> 這部分主要是在說明，某些公司若決定採用雲端方式來經營公司，他們所採取的策略為何。遷移策略是指遷移公司的設備。

- 重新託管 Rehosting
  - 又稱作「搬運轉移」、「工作負載平移」
  - 移動舊有的應用程式，但**不需要修改**。 
- 重組平台 Replatforming
  - 「精進平移」、「微調搬遷」
  - 類似工作負載平移，但會進行雲端最佳化
  - 雲端最佳化作業以達成實際效益。
  - 最佳化**不需要改變應用程式的核心架構**。
- 重構/重新架構 Refactoring/re-architecting
  - 使用**雲端原生功能**重新設計應用程式的架構和開發方式，否則無法達到目標。
  - 要寫 code
  - 最高初期成本(e.g. 寫code人員)
- 重新購買 Repurchasing
  - 從傳統授權轉移到軟體即服務模型。
- 保留 Retaining
  - 不轉到 AWS 雲端
  - 某些設備還可以運行，但未來可能會被淘汰，所以就先保留但也不遷移到雲端上
- 淘汰 Retiring
  - 不轉到 AWS 雲端

## AWS Snow 系列
- 實體裝置的集合，可協助以實體方式將 EB 級資料輸出入 AWS。 
- 由 AWS 擁有和管理，並與 AWS 安全、監控、儲存管理和運算功能整合。 

![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715482800/tk6lyKxY5HH_oG1SyiGBOw/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/9UQ06syJy6q8YfWq_KuUQCm7eheL9hqqb.jpg)

###  AWS Snowcone
- 小型、堅固且安全的邊緣運算與資料傳輸裝置。 
- 配備 2 個 CPU、4 GB 記憶體，以及多達 **14 TB** 的可用儲存空間。
### AWS Snowball  
- Snowball Edge Storage Optimized 
  - 非常適用於**大規模資料遷移和週期性傳輸工作**流程，以及具較高容量需求的本機運算。 
  - 儲存：為區塊磁碟區以及 Amazon S3 相容物件儲存提供 **80 TB** 的硬碟 (HDD) 容量，並為區塊磁碟區提供 1TB SATA 固態硬碟 (SSD)。 
  - 運算：40 個 vCPU 和 80 GiB 的記憶體，支援 Amazon EC2 sbe1 執行個體 (相當於 C5)。
- Snowball Edge Compute Optimized 
  - 為機器學習、全動態影片分析、分析及本機運算堆疊等使用案例提供強大的運算資源。 
  - 儲存：為 Amazon S3 相容物件儲存或 Amazon EBS 相容區塊磁碟區提供 80 TB 的可用 HDD 容量，並為 Amazon EBS 相容區塊磁碟區提供了 28 TB 的可用 NVMe SSD 容量。 
  - 運算：104 個 vCPU、416 GiB 記憶體、以及一個選用的 NVIDIA Tesla V100 GPU。裝置執行 Amazon EC2 sbe-c 與 sbe-g 執行個體 (等同於 C5、M5a、G3 及 P3 執行個體)。
### AWS Snowmobile
-  EB 級($10^{18}$ bytes)的資料傳輸服務，可用來將**大量資料傳輸到 AWS**。 
-  AWS Snowmobile 是長達 45 呎 (13.7 公尺) 的加固貨櫃，由貨櫃聯結車拖行，每輛 AWS Snowmobile 可傳輸高達 **100 PB** 的資料。
> [!NOTE]
> 可以想像前兩個的差別是，snow"cone"表示甜筒，也就是基礎部分；snow"ball"是上面那球冰淇淋。基礎部分提供比較簡易的基本服務，身為冰淇淋靈魂核心的snowball則提供更多、更進階的服務
> snallmobile 顧名思義是行動的，故由貨櫃聯結車處理

## 利用 AWS 服務進行創新
- 創新方法
  - 無伺服器應用程式
    - 不需要您佈建、維護或管理伺服器的應用程式。您不需要擔心容錯能力或可用性。
    - e.g. lambda
  - 機器學習
    - Amazon SageMaker 可將困難的工作從流程中排除，並讓您能夠快速建立、訓練和部署 ML 模型。
  - 人工智慧
    - Amazon CodeWhisperer 在編寫程式碼時取得程式碼建議，並找出程式碼中的安全問題。
    - Amazon Transcribe 將語音轉換為文字。
    - Amazon Comprehend 發現文字中的模式。
    - Amazon Fraud Detector 識別潛在的線上詐騙活動。
    - Amazon Lex 建立語音和文字 Chatbot。
> [!NOTE]
> - AWS DeepRacer 是一輛 1/18 比例的無人賽車，可用於測試強化學習模型。
> - Amazon Textract 這項機器學習服務可從掃描的文件中自動擷取文字和資料。
