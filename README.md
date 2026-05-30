# my-classroom-tools

班級互動工具總專案，用來集中管理高職汽車科、高職數學與課堂互動網頁工具。

## 目標

- 快速建立可直接上課使用的互動網頁工具。
- 讓學生以低門檻方式參與課堂。
- 支援鷹架教學、學思達流程、即時回饋與資料保存。

## 目錄

- `tools/`：每一個班級工具的子資料夾。
- `CLAUDE.md`：Codex 工作藍圖。
- `firestore.rules`：Firebase Firestore 安全規則。

## 安全

- 不存真實學生姓名或身分證字號。
- 不提交 `.env`、金鑰、憑證或 `.claude/`。
- 新增 Firebase 集合前，先確認 Security Rules。
