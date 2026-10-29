# MY WARDROBE V3｜GitHub Pages iPhone 離線 PWA

本版只為使用者已上線的 **MY-WARDROBE-V3** 儲存庫補上 PWA 離線功能；沿用 40 組長褲／80 張 A/B、5 組短褲與全部原有篩選功能。

## 上傳方式

1. 解壓縮 ZIP；把 `index.html`、`sw.js`、`manifest.webmanifest`、`README.md`、`.nojekyll`、完整 `icons/` 資料夾**一起**上傳到 GitHub 儲存庫根目錄。既有 `index.html`、`README.md` 請覆蓋，其餘新增。
2. GitHub → Settings → Pages → Deploy from a branch → `main` / `(root)`。確認新的 Commit 已部署。
3. 請**打開 Pages 正式網址**，不要打開 `github.com/...` 的儲存庫檔案頁。Pages 預設網址格式：`https://<帳號>.github.io/MY-WARDROBE-V3/`（以 Settings → Pages 顯示的實際網址為準）。

## iPhone 離線驗收

1. iPhone 連網、使用 Safari 開啟新版 Pages 網址，完整載入穿搭圖。
2. 等首次 Service Worker 安裝完成，建議關閉頁面再開啟一次、確認仍正常。
3. Safari 分享 → 加入主畫面 → 開啟為 Web App（若有此開關）→ 加入。
4. **先開啟主畫面圖示一次並正常載入，再開啟飛航模式（Wi-Fi 也關閉）**，完全關閉該 Web App，再從主畫面重開。
5. 驗收：長褲 A/B、短褲四單品、指定外套 B-only、上一組下一組、圖片放大、換一組均可在無網路下使用。

## 故障排除

- 開啟 `https://<帳號>.github.io/MY-WARDROBE-V3/sw.js`，應顯示 JavaScript，而不是 GitHub 404 或 HTML。`/manifest.webmanifest` 也應能開啟。
- 若仍離線失敗，先確認 GitHub Pages 新版本部署完成，Safari 連網重新開啟 1～2 次；必要時刪除舊主畫面圖示、清除此網站資料後重加，避免舊快取。
- **不是離線 HTML 檔案**：本包需先在 HTTPS 的 GitHub Pages 開啟，Service Worker 才能安裝。用 `file://` 雙擊檔案測試時，無法驗證離線 PWA 安裝。
- 靜態商品圖片均嵌於 `index.html`，所以離線可看。若點擊商品連結跳往外部商店，外部網頁仍需網路。
- iOS 可以在儲存空間不足或長期未使用時清理網站快取；離線功能是經安裝與快取後可用，不是永久不可清除的離線保證。
- 更新網頁時需一併更新 `sw.js` 的 CACHE_NAME（例如 r1 → r2），使離線內容可更新；請保留 HTML 及全部圖檔等源始備份。

## 隱私提醒

GitHub Pages 公開專案的 HTML、內嵌穿搭圖與商品清單可被任何訪客讀取。
