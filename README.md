# gem5_HW

---

## 檔案

- 所有檔案目前皆位於 `master` 分支。

---

## 結果

`gem5_result` 資料夾中包含以下模擬結果：

- `m5out_2way` 、 `m5out_fullway` - 問題三的模擬結果
- `m5out_LRU`、`m5out_FBR` - 問題四的模擬結果
- `m5out_wb`、`m5out_wt` - 問題五的模擬結果

---

## gem5 修改紀錄

### 1. L3 Cache Replacement

- 所在檔案：  
  `Caches.py`

- 修改內容：
  - 為 L3 Cache 新增 **FBR replacement policy**，但他會顯示叫LFU
  - 若不使用可註解掉

---

### 2. Replacement Policy

- 所在檔案：  
  `lfu_rp.cc`、`lfu_rp.hh`

- 修改內容：
  - 雖然他叫lfu_rp，但我把內容改成FBR了

---

### 3. Write Policy切換

- 所在檔案：  
  `base.cc`  
  修改位置約在第 **1070 行附近**。

- 修改內容：
  - 增加 Write-Through。
  - **目前應為 Write-Back 模式**（Write-Through 已註解）。

  > 如需啟用 Write-Through，可取消註解。

---
### 4. 第二次上傳

- 修改demo的問題
- 好像是l2cache size太大，導致資料都不需要到l3cache就被解決了

---
### 5. 總共修改檔案

- Options.py
- Caches.py
- Xbar.py
- BaseCPU.py
- CacheConfig.py
- base.cc
- lfu_rp.cc
- lfu_rp.hh

