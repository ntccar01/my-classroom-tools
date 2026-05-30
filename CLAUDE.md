# my-classroom-tools — 我的班級工具總專案

## 對話開始時請先讀
進度與最近更動都在 Obsidian：`secondbrain/my-classroom-tools/工作筆記.md`

## 工作模式
- **加新工具**：對 Codex 說「我想做一個 XXX 工具」，Codex 會建 `tools/<工具名>/` 子資料夾並引導開發。
- **結束工作**：對 Codex 說「收工」，請更新 Obsidian 工作筆記，commit + push GitHub。
- **接續工作**：對 Codex 說「讀工作筆記、告訴我上次做到哪」。

## 工作桌 + 三個家
- GDrive 工作桌：`G:\我的雲端硬碟\my-classroom-tools\`
- GitHub repo：`ntccar01/my-classroom-tools`
- Obsidian 駕駛艙：`secondbrain/my-classroom-tools/工作筆記.md`
- Firebase 專案：`my-teaching-tools` (`my-teaching-tools-92611`)
- Supabase 專案：`my-teaching-tools` (`flkbnsxauznqisvriuso`)

## 教學背景
- 使用者主要教授高職汽車科相關課程，也教授高職數學。
- 主要年級為 10-12 年級（高職一到三年級）。
- 學生多為學習低成就與學習意願低落者。
- 工具設計優先採用鷹架理論，可搭配學思達教學法。
- 偏好把課程做成互動網頁，方便投放教室與學生操作。

## 工具清單
（之後加新工具時會自動更新）
- （尚無）

## 工作注意事項
- 學生資料一律去識別化，只用座號、班級代號或匿名代碼。
- commit 訊息要寫清楚做了什麼與為什麼。
- 收工前說「收工」讓 Codex 同步 GDrive、GitHub、Obsidian。
- Firebase 前端公開集合必須先寫 Security Rules；正式學生資料不得公開讀寫。
- 不要把 token、service role key、`.env` 或 `.claude/` commit 到公開 repo。
