# 第 4 站 網頁簡報

要讀的字都用網頁做，不要叫生成模型畫字。

1. 每個 `slide` 寫成一頁 HTML，尺寸固定等於成片（1920x1080 或 1080x1920）。
2. 動畫全部寫在 `window.onFrame(ms)`，依時間計算，**不要用 CSS animation 或 setTimeout**，這樣每一格截圖都一樣。骨架在 `templates/scene.html`。
3. 用 headless Chrome（puppeteer-core 或 playwright）每格呼叫 `onFrame`、截圖，再用 ffmpeg 合成影片。
4. 右下角留 300x300 給講師小窗，底部留字幕高度。
5. 截圖檢查：字沒有超出、沒有壓到小窗、手機上看得清楚（內文至少 28px）。
