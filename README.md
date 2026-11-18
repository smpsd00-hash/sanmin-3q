# 三民國小 3Q 小達人網站｜漫畫路徑修復版

## 本次修復
- 四張漫畫圖片改用純英文檔名，避免中文檔名在 ZIP 解壓、GitHub 上傳或 CDN 路徑編碼時不一致。
- `comics.json` 已同步更新四張圖片路徑。
- 保留 AQ、EQ、MQ 與 3Q 綜合篇四個分類。

## 部署方式（重要）
1. 解壓縮本 ZIP。
2. 開啟解壓後的資料夾。
3. 將資料夾**裡面的所有內容**上傳至 GitHub Repository 的網站根目錄（不是把外層資料夾整個再包一層）。
4. 確認 GitHub 根目錄直接看得到 `index.html`、`comics.json`、`comics/`、`assets/`。
5. 確認 `comics/` 資料夾內有四個 `.webp` 檔案。
6. 等待 Netlify 部署完成，再以 Ctrl+F5 強制重新整理。

## 檔案結構
```
index.html
comics.json
comics/
  01-AQ-robot-comeback.webp
  02-EQ-emotional-intelligence.webp
  03-MQ-integrity-competition.webp
  04-3Q-super-adventure.webp
assets/
netlify.toml
```
