# Global Infrastructure and Reliability
## Global Infrastructure 全球基礎設施
### 選取區域
- 視公司及位置而定，您可能需要在特定區域執行資料。
- 選取與客戶相近的地區，可協助您更快速地讓他們取得內容。
- 不同區域不一定都有所有功能。
- 服務的成本可能因地區而異。

### Availability Zones / 可用區域
- 可用區域是區域內的一個資料中心或一組資料中心。
- 可用區域在 AWS 全球基礎設施中是完全分隔的。
- 擬定失敗計畫，並在多個可用區域部署應用程式，是建立有彈性且高度可用的架構時必要的動作。
  - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715310000/sigGosoKSxSPrsboXWgt-Q/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/LursH_vFA_JJwpJh_X7EEDdg9hO0gI3M0.png)
  - ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715310000/sigGosoKSxSPrsboXWgt-Q/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/7FT7qRCKYDuvRtkp_omx-6Wi43nlQimul.png)
  - AWS Outposts 將 AWS 基礎設施和服務延伸到不同的位置，包括您的內部部署資料中心。

## Edge Location 節點
- Amazon CloudFront 用來將內容的快取副本存放在更靠近客戶位置的站點，以便加快交付。
  - Amazon CloudFront 是一種內容交付服務。這項服務使用節點網路來快取內容，並將內容交付給世界各地的客戶。內容經過快取後，會以副本形式存放在本機。這些內容可能是影片檔案、相片、網頁等。
- ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715310000/sigGosoKSxSPrsboXWgt-Q/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/CgPtp0K4ZJrvbhOl_hGFL1EyBbeUcy4Of.png)

## 佈建資源
### 與 AWS 服務互動的方式
- AWS 管理主控台
- AWS 命令列界面 (AWS CLI)
  - 透過指令碼來自動化 AWS 服務和應用程式動作。
- 軟體開發套件 (SDK)
  - 透過專為程式設計語言或平台設計的 API，用程式碼執行 AWS 服務。

### 佈建
- AWS Elastic Beanstalk
  - 調整容量
  - 負載平衡
  - 自動擴展
  - 應用程式運作狀態監控
- AWS CloudFormation
  - 可以透過撰寫程式碼行來建立環境，無需使用 AWS 管理主控台個別佈建資源。
  - 會在管理堆疊時判斷需要執行的正確作業，並在偵測到錯誤時自動復原變更。

## other 
- AWS Outposts 這項服務可讓您以混合雲端方法執行基礎設施。
- AWS Fargate 是一種容器專用的無伺服器運算引擎。
- Amazon Simple Queue Service (Amazon SQS) 這項服務可讓您透過佇列在軟體元件之間傳送、存放和接收訊息。