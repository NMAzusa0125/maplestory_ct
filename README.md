# maplestory_ct
🍁 楓之谷 Artale 楓葉萬事屋
一個專為楓之谷 Artale 玩家設計的代售代收道具交易管理系統，結合現代化前端介面與 Google 試算表後端，提供便捷的交易記錄管理功能。
✨ 功能特色
📋 交易管理

📤 代售委託 - 管理玩家委託代售的道具
📥 代收委託 - 管理玩家委託代收的道具
🔄 即時同步 - 與 Google 試算表即時同步所有交易資料
📊 統計儀表板 - 即時顯示交易統計資訊

🎯 智能功能
💰 自動手續費計算 - 裝備類道具 20%，其他道具 10%
👥 多用戶支援 - 支援多個委託人管理
🏷️ 道具分類 - 裝備、捲軸、任務道具、礦物等分類
📱 響應式設計 - 完美支援手機和桌面裝置

🔧 技術特點
🌐 純前端應用 - 可直接在 GitHub Pages 部署
🔒 CORS 完全解決 - 使用 JSONP 技術避免跨域問題
💾 本地儲存 - API 設定自動保存
⚡ 高效能 - 輕量化設計，載入快速

🚀 快速開始: 前置需求
Google 帳號
現代化瀏覽器 (Chrome, Firefox, Safari, Edge)

部署步驟
1. 設定 Google Apps Script 後端
前往 Google Apps Script
點擊「新增專案」
將 gas-backend.js 的內容複製到編輯器中
修改 SPREADSHEET_ID 為你的 Google 試算表 ID
點擊「部署」→「新增部署作業」
設定類型為「網頁應用程式」
執行身分選擇「我」
存取對象選擇「任何人」
點擊「部署」並複製取得的網址

2. 建立 Google 試算表
前往 Google 試算表
建立新的試算表
從網址列複製試算表 ID (在 /spreadsheets/d/ 和 /edit 之間的部分)
將此 ID 更新到 Google Apps Script 的 SPREADSHEET_ID 變數中

3. 部署前端
方法一：GitHub Pages (推薦)

Fork 這個專案或下載 index.html
上傳到你的 GitHub 儲存庫
在儲存庫設定中啟用 GitHub Pages
訪問你的 GitHub Pages 網址

方法二：本地執行

下載 index.html 檔案
直接在瀏覽器中開啟

4. 系統設定
開啟部署好的網頁
在「雲端同步設定」區域輸入 Google Apps Script API 網址
點擊「測試連線」確認連接成功
開始使用系統！

📖 使用說明

點擊「📤 代售委託」標籤
填寫道具資訊：
道具名稱
道具類型 (影響手續費率)
委託人 (賣家)
道具數量
備註 (選填)

點擊「📥 代收委託」標籤
填寫道具資訊：
道具名稱
道具類型
委託人 (買家)
道具數量
備註 (選填)


在「📋記錄」區域可以查看所有交易
使用標籤篩選：全部、代售、代收、待處理
點擊「🔄重整」同步最新資料

手續費說明
裝備類道具：20% 手續費
其他道具：10% 手續費
系統會自動計算實收金額

⌨️ 快捷鍵
Ctrl + R - 重新載入交易記錄
Ctrl + T - 測試 API 連線

📂 檔案結構
maplestory-artale-trading-system/
├── index.html              # 前端主要檔案 (完整應用)
├── gas-backend.js          # Google Apps Script 後端代碼
└── README.md              # 專案說明文件
🔧 技術架構
前端技術

HTML5 - 結構化內容
CSS3 - 現代化樣式，支援動畫和響應式設計
JavaScript (ES6+) - 純前端邏輯，無需框架
JSONP - 跨域 API 請求技術

後端技術
Google Apps Script - 雲端執行環境
Google Sheets API - 資料儲存和管理
RESTful API - 標準化 API 介面

資料結構
javascript// 交易記錄格式
{
  timestamp: "2024-01-01T12:00:00.000Z",
  tradeType: "consignment" | "purchase",
  itemName: "道具名稱",
  itemType: "equipment" | "scroll" | "quest" | "mineral" | "bag" | "potion" | "cash",
  client: "委託人",
  seller: "賣家",
  buyer: "買家", 
  quantity: 1,
  notes: "備註",
  status: "pending" | "completed"
}

🔒 安全性考量
✅ 所有資料儲存在你自己的 Google 試算表中
✅ API 金鑰和敏感資訊不會暴露在前端
✅ 使用 Google 的安全認證機制
✅ 支援 HTTPS 加密傳輸

🐛 故障排除，常見問題:
Q: 顯示「連線測試失敗」
確認 Google Apps Script 已正確部署
檢查 API 網址是否正確
確認部署權限設為「任何人」

Q: 提交表單後沒有反應
檢查瀏覽器控制台是否有錯誤訊息
確認網路連線正常
嘗試重新整理頁面

Q: 交易記錄顯示空白
確認 Google 試算表 ID 正確
檢查試算表是否有資料
點擊「重新整理」按鈕

Q: 手機版介面異常
確保使用現代化瀏覽器
嘗試橫向顯示
清除瀏覽器快取

🤝 貢獻指南
歡迎提交 Issue 和 Pull Request！
提交 Bug 報告


主要開發者 - Azusa

🙏 致謝
感謝楓之谷 Artale 社群的支持
感謝所有測試用戶的反饋
使用到的開源專案和工具

📞 聯絡方式

GitHub Issues: https://github.com/NMAzusa0125/maplestory_ct
Email: kcazusa1225@gmail.com