# 三民國小 3Q 小達人網站 V4

本版本將網站使用的圖片與下載文件統一採用英文檔名，降低中文網址編碼、空格與跨平台路徑差異造成的錯誤。網站同時支援 GitHub Pages（專案網站）與 Netlify 靜態部署。

## 目錄結構

```text
sanmin-3q/
├── index.html
├── comics.json
├── netlify.toml
├── .nojekyll
├── comics/
│   ├── 01-AQ-robot-comeback.webp
│   ├── 02-EQ-emotional-intelligence.webp
│   ├── 03-MQ-integrity-competition.webp
│   └── 04-3Q-super-adventure.webp
└── assets/
    └── documents/
        ├── 3q-teacher-forms.docx
        ├── sanmin-3q-implementation-plan.docx
        └── hsinchu-3q-selection-plan-115.odt
```

## 更新 GitHub（重要）

1. 進入 `smpsd00-hash/sanmin-3q`。
2. 切換到 `main` 分支（GitHub Pages 目前從 `main / (root)` 發布）。
3. 將本套件內的**全部檔案與資料夾內容**上傳至 Repository 根目錄，保留上述目錄結構；不要只上傳 ZIP，也不要多包一層 `sanmin-3q-v4` 資料夾。
4. 同名檔案選擇覆蓋，並提交到 `main`。
5. 等待 GitHub Pages workflow 完成，再測試網站。
6. Netlify 若連結同一 Repository 的 `main` 分支及根目錄，會自動重新部署；若 Netlify 指向其他分支，需將同一套檔案同步到 Netlify 使用的發布分支。

## 測試網址（GitHub Pages）

- 網站：`https://smpsd00-hash.github.io/sanmin-3q/`
- AQ 漫畫：`https://smpsd00-hash.github.io/sanmin-3q/comics/01-AQ-robot-comeback.webp`
- EQ 漫畫：`https://smpsd00-hash.github.io/sanmin-3q/comics/02-EQ-emotional-intelligence.webp`
- MQ 漫畫：`https://smpsd00-hash.github.io/sanmin-3q/comics/03-MQ-integrity-competition.webp`
- 3Q 漫畫：`https://smpsd00-hash.github.io/sanmin-3q/comics/04-3Q-super-adventure.webp`
- 教師表單：`https://smpsd00-hash.github.io/sanmin-3q/assets/documents/3q-teacher-forms.docx`
- 校內實施計畫：`https://smpsd00-hash.github.io/sanmin-3q/assets/documents/sanmin-3q-implementation-plan.docx`
- 市級甄選計畫：`https://smpsd00-hash.github.io/sanmin-3q/assets/documents/hsinchu-3q-selection-plan-115.odt`

## 新增漫畫

1. 將圖片轉為 WebP，使用英文檔名放入 `comics/`。
2. 編輯根目錄 `comics.json`，新增 `category`、`title`、`description`、`src`、`alt`。
3. `src` 使用相對路徑，例如 `comics/05-new-story.webp`。
4. 圖片與 `comics.json` 一起提交到發布分支。

## 新增教師文件

將文件放入 `assets/documents/`，檔名使用小寫英文、數字與連字號；再於 `index.html` 的教師資源區新增相對路徑連結。不要將含學生個資的已填表單上傳公開網站。

## 注意

GitHub Pages 與 Netlify 是不同的發布目標。請確認 Netlify 的 Repository、Branch、Base directory 與 Publish directory：建議使用同一 Repository、`main`、Base directory 留白、Publish directory `.`。
