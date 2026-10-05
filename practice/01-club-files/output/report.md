# 社團活動檔案整理報告 (Club Files Organization Report)

## 一、 整理概要

- **原始資料夾**：`practice/01-club-files/input/`
- **整理目標資料夾**：`practice/01-club-files/output/`
- **處理檔案總數**：12 個檔案
- **原檔狀態**：12 個輸入原檔完全保持不變，未移動、未修改、未刪除。
- **輸出狀態**：成功建立 4 個分類資料夾，各複製一份副本，共 12 個輸出檔案；並建立 `manifest.json` 與本報告 `report.md`。

---

## 二、 分類架構與說明

所有檔案依據其業務性質與用途，歸納為以下 4 大分類：

1. **`01_企畫與備案/`**
   - 收納檔案：`proposal_final.txt`、`proposal_final2.txt`、`rain_plan.txt`
   - 分類依據：活動核心方案、不同備選方案版本以及天候應變計畫。
2. **`02_會議與執行/`**
   - 收納檔案：`meeting_notes.txt`、`next_steps.txt`
   - 分類依據：籌備團隊開會過程之討論要點及後續行動指引。
3. **`03_文宣與回饋/`**
   - 收納檔案：`announcement.txt`、`announcement_copy.txt`、`poster_text.txt`、`feedback_questions.txt`
   - 分類依據：對外宣傳、行前公告以及活動結束後的滿意度回饋問卷題綱。
4. **`04_經費與器材/`**
   - 收納檔案：`budget_draft.txt`、`equipment_list.txt`、`equipment_backup.txt`
   - 分類依據：活動所需之行政耗材預算、器材清單及其備份檔案。

---

## 三、 重複檔案分析（內容完全一致）

經 SHA256 雜湊與全文逐字比對，發現以下兩組檔案內容完全相同：

1. **行前公告組**：
   - `announcement.txt` 與 `announcement_copy.txt`
   - SHA256：`C19164B1054EBF52ED33BC5321C887985EA043A0B07DB1E99F866986D2CCD584`
   - 內文：`SIMULATION / 教學模擬\nBring your own notebook. Time and location are undecided.\n請帶筆記本。時間地點尚未決定。`
   - 處置：依據「不刪除、不覆蓋、各留副本」原則，兩者皆完整複製至 `03_文宣與回饋/`。
2. **器材清單組**：
   - `equipment_list.txt` 與 `equipment_backup.txt`
   - SHA256：`C21D53BA1F8D3AD06E1833539935120A5BACA4D13B34A2AA98CE157FF4502FA3`
   - 內文：`SIMULATION / 教學模擬\nmarkers: 4\npaper packs: 2`
   - 處置：兩者皆完整複製至 `04_經費與器材/`。

---

## 四、 疑似重複但內容相異之版本（待確認問題）

### 1. 企畫版本歧異（核心重點）
- **涉及檔案**：`proposal_final.txt` 與 `proposal_final2.txt`
- **內容對比**：
  - `proposal_final.txt`：`Proposal v1: outdoor activity, 30 minutes. / 企畫第一版：戶外活動，30分鐘。尚未定案。`
  - `proposal_final2.txt`：`Proposal v2: indoor activity, 20 minutes. / 企畫第二版：室內活動，20分鐘。仍待討論。`
- **待確認問題與分析**：
  - 檔名雖然皆包含「final」，但內容為完全不同的兩種活動設計（一為戶外 30 分鐘，一為室內 20 分鐘）。
  - **切勿以檔名「final」或「final2」判定為最終版**，兩份文件均明文記載「尚未定案/仍待討論」。
  - 依據 `meeting_notes.txt`（下次討論室內或室外方案）及 `next_steps.txt`（比較兩個企畫，兩者都尚未定案），這兩份企畫仍需由活動團隊開會定奪，不能隨意淘汰任一份。

### 2. 其他行政待確認事項
- **預算尚未核定**：`budget_draft.txt` 載明紙張預算為模擬值 100，尚未獲得核定，需於定案後向幹部或指導單位確認。
- **雨天方案關聯**：`rain_plan.txt` 指出「下雨時另議室內方案」，是否直接以 `proposal_final2.txt`（室內活動）作為下雨備案，需待主辦幹部釐清確認。
- **集合時間與地點**：`announcement.txt` 提及「時間地點尚未決定」，待企畫定案後需重新發布正式公告。

---

## 五、 檢查成果清單

### 實際做過的檢查
1. **原檔完整性檢驗**：確認原始 `input/` 目錄內的 12 個檔案均存在，無任何檔案被刪除、改名或更動。
2. **複製檔案數量檢驗**：確認 `output/` 4 個分類資料夾內共有 12 個檔案副本，無一遺漏。
3. **檔案完整性（雜湊）檢驗**：對 12 個輸出複本與 12 個原始輸入檔案分別計算 SHA256 雜湊，比對結果 100% 一致，確認複製過程內容無任何修改或損壞。
4. **格式合規性檢驗**：確認 `manifest.json` 頂層為合法陣列，包含 12 筆物件，每筆均有 `source`、`destination` 與 `reason` 欄位。

### 還沒確認（需人工介入）的部分
1. **企畫二選一的決策**：究竟採用「戶外版 30 分鐘」還是「室內版 20 分鐘」，需由真人主辦人確認。
2. **完全重複檔案之後續留存**：`announcement_copy.txt` 與 `equipment_backup.txt` 在確認備份無誤後，未來是否要正式歸檔或清理，需依社團檔案管理規則決定。
3. **空白資訊之補齊**：活動時間、地點與正式預算金額尚未填寫確認。
