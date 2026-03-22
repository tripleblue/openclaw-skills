---
name: gen-pic
description: 使用 Google Gemini 生成圖片。當用戶要求生成圖片、使用 Gemini 產生圖像、或需要 AI 圖片生成時觸發。
---

# gen-pic - Gemini 圖片生成

## 使用情境
- 用戶要求生成圖片
- 用戶要求使用 Gemini 產生圖像

## 執行步驟

1. **開啟 Gemini 網站**
   ```
   使用 browser 工具開啟 https://gemini.google.com/app
   profile: openclaw
   ```

2. **點擊「生成圖片」按鈕**
   - 找到帶有 🖼️ 圖示的按鈕
   - 使用 act + click 點擊

3. **輸入提示詞**
   - 點擊文字輸入框
   - 使用 type 輸入用戶想要的圖片描述

4. **發送請求**
   - 點擊「傳送訊息」按鈕

5. **等待生成**
   - 等待約 10-15 秒讓 AI 生成圖片

6. **下載圖片**
   - 點擊「下載原尺寸」按鈕
   - 檔案會下載到：`~/Downloads/`

7. **取得最新下載的檔案**
   - 列出下載資料夾：`ls -la ~/Downloads/`
   - 選擇最新產生的檔案（時間戳記最新的 .png 檔）

8. **複製到允許的目錄**
   - 因為 message 工具只能讀取允許的目錄（如 ~/.openclaw/workspace/download/）
   - 執行：`cp ~/Downloads/<檔名> ~/.openclaw/workspace/download/`

9. **傳送給用戶**
   - 使用 message 工具傳送圖片
   - **重要：使用下載的原始檔案，不要使用截圖**
   - 目標管道：自動判斷（從用戶訊息的 channel metadata 取得）
   - 使用複製後的路徑（如 ~/.openclaw/workspace/download/<filename>）

10. **關閉分頁**
   - 關閉該分頁

## 注意事項
- 如果遇到 tab not found 錯誤，重新開啟新分頁
- Gemini 有時會生成多張圖片，選擇一張傳給用戶
- **務必傳送原始下載檔案（~/Downloads/），而非截圖**
