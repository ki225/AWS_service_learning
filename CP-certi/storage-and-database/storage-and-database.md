# storage and database
## Instance Stores and Amazon Elastic Block Store (Amazon EBS)
### Instance Stores 
- 為 Amazon EC2 執行個體(虛擬伺服器)提供臨時區塊層級儲存。
  - 區塊層級儲存磁碟區的行為與實體硬碟相似。
- 執行個體終止時，資料會遺失，即使重新啟動也不復原。

### Amazon Elastic Block Store (Amazon EBS)
- 用於在資料庫上新增快取層，以**改善常見請求讀取時間**。
- 用於提供區塊式存放磁碟區
  - 可搭配 Amazon EC2 執行個體使用。如果**停止/終止執行個體，連接的 EBS 磁碟區上的所有資料仍然可用**。
  - 將磁碟機從 EC2 執行個體的主機電腦分開
- 定義組態 (例如磁碟區大小和類型) 並加以佈建。
- 建立 Amazon EBS snapshots，以建立 EBS 磁碟區(volume)的增量備份。
  - snapshot其實就是增量備份
    - 增量備份與完整備份不同，每次進行完整備份時，會複製存放磁碟區中的所有資料。完整備份包含自最近一次備份之後未變更的所有資料。
- ![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715338800/z3RSfo9PkdHbB6sMGh8ooA/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/nXZ5gc23EZqGP14Y_M_2Hzp9gRvoP1UzK.png)


## Amazon Simple Storage Service (Amazon S3)
### 物件儲存
![](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1715338800/z3RSfo9PkdHbB6sMGh8ooA/tincan/50bb3ae9507c15309a6ecbb7b8d96d9cb455d06f/assets/s2tR3DISOzqvwpLv_UvOIBdfsF3m1xXl8.png)

- Amazon S3 能提供無限的儲存空間。
- 單一物件的檔案大小上限為 5 TB。
> [!WARNING]
> Amazon S3 儲存貯體不能連接到 Amazon EC2 執行個體
### 種類
- S3 Standard 
  - 專為經常存取的資料設計
  - 至少將資料存放在三個可用區域
  - 相較於其他專為不常存取的資料和封存儲存設計的儲存類別相比，成本較高
- Amazon S3 Standard-IA 
  - 非常適合不常存取的資料、立即使用
  - 類似 Amazon S3 Standard，將資料至少存放在三個可用區域。
  - 儲存價格較低、擷取價格較高，適合不常存取但在需要時具備高可用性的資料
- S3 One Zone-IA
  - 將資料存放在單一可用區域中    
    - 適合在可用區域故障時，使用者可以輕鬆地重現資料。
  - 存放價格比 Amazon S3 Standard – IA 低
- S3 Intelligent-Tiering 
  - 非常適合存取模式未知或持續變更的資料，Amazon S3 會監控物件的存取模式
  - 每個物件都需要小額每月監控和自動化費用
  - 如果連續 30 天未存取物件，Amazon S3 會自動將物件移至不常存取層，即 **S3 Standard-IA**。
  - 如果存取了不常存取層中的物件，Amazon S3 會自動將其移至頻繁存取層，即 **S3 Standard**。
- S3 Glacier Instant Retrieval 
  - 適用於需要立即存取的封存資料
  - 可以在幾毫秒內擷取物件
- S3 Glacier Flexible Retrieval 
  - 專為資料封存所設計的低成本儲存
  - 能夠在幾分鐘到幾小時內擷取物件
  - 適合用於資料封存，e.g. 客戶記錄或較舊的相片和影片檔案
- S3 Deep Archive
  - 非常適合封存、成本最低的物件儲存類別
  - 能夠在 12 小時內擷取物件
  - 支援長期保留和數位保留，適用於一年中可能存取一次或兩次的資料
  - 是 AWS 雲端中成本最低的儲存，資料擷取時間為 12 到 48 小時。
  - 會複寫並儲存在至少三個分散各地的可用區域。
- Amazon S3 Outposts 
  - 在 Amazon S3 Outposts 上建立 S3 儲存貯體
  - 可更輕鬆地在 AWS Outposts 上擷取、儲存和存取資料
  - Amazon S3 Outposts 設計用於將資料以持久及備援方式儲存在 Outposts 上的多個裝置和伺服器上。
    - 嚴苛效能需求
    - 適合具有本機資料駐留需求的工作負載
    - 需求必須將資料存放在內部部署應用程式附近


### 比較 Amazon EBS 和 Amazon S3
如果是使用完整的物件，或僅偶爾進行變更，S3 比較理想。
如果要執行複雜的讀取、寫入或變更功能，則 EBS 顯然更勝一籌。


## Amazon Elastic File System (Amazon EFS)
### 檔案儲存
- 多個用戶端 (例如使用者、應用程式、伺服器等) 可以存取存放在共用檔案資料夾中的資料。
- 儲存伺服器會使用具有本機檔案系統的區塊儲存來整理檔案。用戶端透過檔案路徑存取資料。
- 適合需要同時存取相同資料的大量服務和資源的使用案例。
### Amazon Elastic File System (Amazon EFS)
- 可擴展的檔案系統
  - 依需求擴展至 PB 資料，而不會中斷應用程式。
- 區域性服務
  - 在多個 AZs (available zones)存放資料
### 比較 Amazon EBS 和 Amazon EFS
- Amazon EBS
  - 若要連接 EC2 和 EBS 磁碟區，兩者必須在相同 AZ --> 單一 AZ

## Amazon Relational Database Service (Amazon RDS)
### Amazon Relational Database Service (RDS)
- Relational Database：資料會以與其他資料建立關聯的方式存放。
  - 結構式查詢語言 (SQL) 
- 可自動執行硬體佈建、資料庫設定、修補和備份等工作。
- 提供了許多不同的安全選項
- 可在六個資料庫引擎上使用
  - Amazon Aurora
    - 企業級的關聯式資料庫
    - 會在三個可用區域中複寫六份資料副本，並持續將資料備份到 Amazon S3。
    - 與 MySQL 和 PostgreSQL 關聯式資料庫相容。
    - 透過減少不必要的輸入/輸出 (I/O) 操作來降低資料庫成本，同時確保資料庫資源保持可靠且可用。 
      - 比標準 MySQL 資料庫快上五倍，而且比標準 PostgreSQL 資料庫快上三倍。
  - PostgreSQL
  - MySQL
  - MariaDB
  - Oracle Database
  - Microsoft SQL Server


## Amazon DynamoDB
- 非關聯式資料庫
  - 又稱為「NoSQL 資料庫」
  - 鍵值對。
- 在任何規模下達到 10 毫秒內的效能。
- 每天最多可擴展 10 兆個請求
- 無伺服器
  - 不需管理、佈建、維修伺服器
- 自動擴展

## Amazon Redshift
- 可用於**大數據分析**的資料倉儲服務。
- 提供從許多來源收集資料的能力，並協助了解資料中的關係和趨勢。

## AWS Database Migration Service(AWS DMS)
- 在來源資料庫和目標資料庫之間移動資料。
  - 來源和目標資料庫可以是相同或不同的類型。
  - 資料庫合併
  - 連續複寫
    - 將進行中的資料副本傳送到其他目標來源
  - 開發、測試資料庫遷移
    - 不影響使用者

## 其他資料庫服務
- Amazon DocumentDB
  - 支援 MongoDB 工作負載的文件資料庫服務。(MongoDB 是一種文件資料庫程式。)
- Amazon Neptune
  - [圖形資料庫服務(NoSQL)](https://aws.amazon.com/tw/nosql/graph/)
  - 建置和執行可搭配高度關聯資料集使用的應用程式
    - 例如推薦引擎、詐騙偵測和知識圖譜。
- Amazon Quantum Ledger Database (Amazon QLDB)
  -  一種總帳資料庫服務。 
  -  檢閱您對應用程式資料所做的所有變更完整記錄。
-  Amazon Managed Blockchain
   -  使用開放原始碼架構來建立和管理區塊鏈網路。 
   -  區塊鏈是一種分散式總帳系統，允許多方在沒有中央權限的情況下，執行交易和共用資料。
-  Amazon ElastiCache
   -  用於在資料庫上新增快取層，能夠協助改善常見要求的讀取時間。 
   -  它支援兩種類型的資料存放區：Redis 和 Memcached。 
-  Amazon DynamoDB Accelerator (DAX)
   -  是適用於 DynamoDB 的記憶體內快取。 
   -  縮短回應時間，從不到十毫秒縮短到數微秒。