### 簡化版 Git Flow 規則說明

#### 1. main 主線分支

- **用途**: 
  - main 主線分支是從 dev 分支合併過來的主線，用於準備和發布的代碼版本。

- **規則**:
  - 僅允許從 dev 分支合併，開發者不能直接在此分支上提交變更。
  - 確保所有開發者的工作最終匯總到共同的版本。
  - 進行最後的錯誤修復和相容正式環境的調整。
  - 合併到 main 分支後，刪除原有的 dev 分支以保持倉庫整潔。

#### 2. dev 開發分支

- **用途**: 
  - dev 分支是所有開發者的基礎分支，所有新的功能開發和修改都從這裡開始。

- **規則**:
  - 開發者從 dev 分支分叉出自己的分支，命名為 `dev-<開發者名稱>`或`dev-<更新名稱>`。
  - 所有功能開發和修改在開發者自己的分支上進行。
  - 開發完成並經過充分測試後，合併到 main 分支。
  - 合併前，必須運行功能測試、確認功能正常運行且無嚴重錯誤。
  - 若合併過程中發生衝突，駁回拉取請求，要求先將 main 分支的最新變更合併到 dev 分支，解決衝突後再提交新請求。

#### 3. release 發布分支

- **用途**: 
  - release 分支專門用於伺服器部署流程，從 main 分支合併而來，用於保存最終穩定的發布版本。

- **規則**:
  - release 分支從 main 分支合併而來，確保發布版本的穩定性。
  - 僅允許進行與正式環境相容的錯誤修正，不允許小功能調整。

#### 備註

- 為了確保會議討論的有效性和代碼的留存，每週會議前，開發者需要進行 dev 分支合併到 main 分支的流程。這樣可以確保討論內容基於最新的開發進展，並且所有變更都已被記錄。
