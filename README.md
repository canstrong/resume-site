# 夏可強 Shawn Hsia — 個人履歷網頁 / Personal Resume

雙語（中／英）個人履歷單頁網站。純靜態，可直接部署到 GitHub Pages。
Bilingual (ZH/EN) single-page personal resume. Static site, deploys to GitHub Pages.

## 檔案 / Files
- `index.html` — 網站原始碼（Design Component，可用 Claude Code 直接編輯）
- `support.js` — 前端執行環境 runtime（請勿修改）
- `image-slot.js` — 照片拖放元件
- `.nojekyll` — 讓 GitHub Pages 原樣提供檔案

## 部署到 GitHub Pages / Deploy
1. 把整個資料夾推到一個 GitHub repo（見下方指令）。
2. repo → **Settings → Pages** → Source 選 **Deploy from a branch** → branch `main`、資料夾 `/ (root)`。
3. 幾分鐘後網站會上線於 `https://<你的帳號>.github.io/<repo 名稱>/`。

## 首次推送指令 / First push
```bash
cd resume-site
git init
git add .
git commit -m "Add bilingual resume site"
git branch -M main
git remote add origin https://github.com/<你的帳號>/<repo 名稱>.git
git push -u origin main
```
或用 GitHub CLI 一次建立 + 推送：
```bash
cd resume-site
gh repo create <repo 名稱> --public --source=. --push
```

## 之後用 Claude Code 修改 / Editing later
直接編輯 `index.html` 即可。內容資料集中在檔案下方 `<script data-dc-script>` 內的 `const DATA = { zh: {...}, en: {...} }`，改文字只要改這個物件。

## 放個人照片 / Add your photo
把照片檔（例如 `photo.jpg`）放進本資料夾，然後在 `index.html` 找到 `<x-import ... id="portrait" ...>` 這一行，改成：
```html
<img src="./photo.jpg" alt="Shawn Hsia" style="width:100%;height:100%;object-fit:cover">
```
