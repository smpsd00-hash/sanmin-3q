# 🌈 三民國小 3Q 小達人網站

以純 HTML、CSS、JavaScript 製作的靜態網站，可直接部署至 GitHub Pages 或 Netlify，不需要 Node.js、資料庫或建置指令。

## 網站內容

- 首頁、3Q 核心理念與 AQ／EQ／MQ 介紹
- 學生互動情境練習與一週 3Q 小任務
- 低、中、高年級教案、教師引導語與可列印學習單
- 校內年度推動時程、觀察指標、典範推薦與評選資訊
- 3Q 繪本漫畫書架（AQ／EQ／MQ 分類）
- 三份來源文件及校內配套表單下載

## 使用與本機預覽

直接開啟 `index.html` 可瀏覽主要網站。若要確認漫畫清單讀取，建議以本機 HTTP 伺服器預覽，例如在此資料夾執行：

```bash
python -m http.server 8000
```

再開啟 `http://localhost:8000`。

## 發布到 GitHub + Netlify

### 1. 建立 GitHub Repository

1. 在 GitHub 建立新的 Repository，例如 `sanmin-3q`。
2. 將本資料夾內的**所有內容**上傳至 Repository 根目錄（不要只上傳 ZIP）。
3. 確認 `index.html` 位於 Repository 根目錄，且 `assets/`、`comics/`、`comics.json` 也在同一層。

### 2. 連結 Netlify

1. 登入 Netlify，選擇 **Add new site → Import an existing project**。
2. 選擇 GitHub 並授權存取剛建立的 Repository。
3. Build settings：
   - Base directory：留白
   - Build command：留白
   - Publish directory：`.`
4. 點選 Deploy。此網站為純靜態 HTML，無需 npm install 或 build。
5. 部署完成後可在 Netlify 的 Domain settings 設定自訂網域。

本專案附有 `netlify.toml`，預設發布目錄為網站根目錄。

## 上架 3Q 漫畫

1. 將漫畫圖片放入 `comics/` 資料夾，建議使用英文小寫檔名，例如 `aq-01.png`、`eq-01.png`、`mq-01.png`。
2. 編輯根目錄的 `comics.json`，依照下列格式加入資料：

```json
[
  {"category":"AQ","title":"AQ 漫畫第 1 頁","src":"comics/aq-01.png"},
  {"category":"EQ","title":"EQ 漫畫第 1 頁","src":"comics/eq-01.png"},
  {"category":"MQ","title":"MQ 漫畫第 1 頁","src":"comics/mq-01.png"}
]
```

3. 將圖片與 `comics.json` 一起 commit、push 到 GitHub。Netlify 會自動重新部署，網站就會更新。
4. 網頁中的「選擇檔案」僅供本機即時預覽，不會上傳伺服器；正式公開請依上述方式將檔案加入 GitHub。

## 重要提醒

- 本網站目前沒有後端、會員登入或資料庫；互動測驗不會儲存學生作答紀錄。
- 不要將含學生姓名、班級、聯絡方式、家庭資訊或未經授權照片的已填表單放到公開 Repository。
- 公開學生故事、照片或作品前，請依學校規範取得適當同意並進行個資保護。
- 網站內容以三民國小校內 3Q 培育及甄選實施計畫、115 年新竹市甄選計畫與配套表單為依據。市級甄選資格、日期、件數及格式每年可能變動，請以當年度正式公告為準。
- 教案、情境題、示範故事及學習單屬於教學延伸素材；示範故事為虛構案例。

## 漫畫專區（已加入正式漫畫）

漫畫圖片已放入 `comics/`，清單由網站根目錄的 `comics.json` 管理。網站載入時會讀取清單並顯示 AQ、EQ、MQ 與 3Q 綜合篇；點擊縮圖可放大閱讀。

目前收錄：
- AQ：逆境智商－三民機器人逆轉勝
- EQ：情緒智商－理解情緒、好好溝通
- MQ：道德智商－正直誠信的競賽風雲
- 3Q：超能冒險－AQ × EQ × MQ 綜合篇

新增漫畫時，請將圖片放入 `comics/`，並在 `comics.json` 增加 `category`、`title`、`description`、`src`、`alt` 欄位。`src` 路徑以 `comics/` 開頭。支援 JPG、PNG、WebP 等瀏覽器可顯示的圖片格式。
