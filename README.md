# maplestory_ct

# 🍁 楓之谷 Artale 楓葉萬事屋

一個專為楓之谷 Artale 玩家設計的代售代收道具交易管理系統，  
結合現代化前端介面與 Google 試算表後端，提供便捷的交易記錄管理功能。

## ✨ 功能特色

### 📋 交易管理
- **📤 代售委託** - 管理玩家委託代售的道具
- **📥 代收委託** - 管理玩家委託代收的道具
- **🔄 即時同步** - 與 Google 試算表即時同步所有交易資料
- **📊 統計儀表板** - 即時顯示交易統計資訊

### 🎯 智能功能
- **💰 自動手續費計算**
- **👥 多用戶支援** - 支援多個委託人管理
- **🏷️ 道具分類** - 裝備、捲軸、任務道具、礦物等分類
- **📱 響應式設計** - 完美支援手機和桌面裝置

### 🔧 技術特點
- **🌐 純前端應用** - 可直接在 GitHub Pages 部署
- **🔒 CORS 完全解決** - 使用 JSONP 技術避免跨域問題
- **💾 本地儲存** - API 設定自動保存
- **⚡ 高效能** - 輕量化設計，載入快速

### 前置需求
- Google 帳號
- 現代化瀏覽器 (Chrome, Firefox, Safari, Edge)

### 部署步驟
#### 1. 設定 Google Apps Script 後端

1. 前往 [Google Apps Script](https://script.google.com/)
2. 點擊「新增專案」
3. 將 `gas-backend.js` 的內容複製到編輯器中
4. 修改 `SPREADSHEET_ID` 為你的 Google 試算表 ID
5. 點擊「部署」→「新增部署作業」
6. 設定類型為「網頁應用程式」
7. 執行身分選擇「我」
8. 存取對象選擇「任何人」
9. 點擊「部署」並複製取得的網址

#### 2. 建立 Google 試算表
1. 前往 [Google 試算表](https://sheets.google.com/)
2. 建立新的試算表
3. 從網址列複製試算表 ID (在 `/spreadsheets/d/` 和 `/edit` 之間的部分)
4. 將此 ID 更新到 Google Apps Script 的 `SPREADSHEET_ID` 變數中

#### 3. 部署前端
**方法一：GitHub Pages (推薦)**
1. Fork 這個專案或下載 `index.html`
2. 上傳到你的 GitHub 儲存庫
3. 在儲存庫設定中啟用 GitHub Pages
4. 訪問你的 GitHub Pages 網址

**方法二：本地執行**
1. 下載 `index.html` 檔案
2. 直接在瀏覽器中開啟

#### 4. 系統設定
1. 開啟部署好的網頁
2. 在「雲端同步設定」區域輸入 Google Apps Script API 網址
3. 點擊「測試連線」確認連接成功
4. 開始使用系統！

## 📖 使用說明

### 新增代售委託
1. 點擊「📤 代售委託」標籤
2. 填寫道具資訊：
   - 道具名稱
   - 道具類型 (影響手續費率)
   - 委託人 (賣家)
   - 道具數量
   - 備註 (選填)
3. 點擊「提交代售委託」

### 新增代收委託
1. 點擊「📥 代收委託」標籤
2. 填寫道具資訊：
   - 道具名稱
   - 道具類型
   - 委託人 (買家)
   - 道具數量
   - 備註 (選填)
3. 點擊「提交代收委託」

### 查看交易記錄
- 在「📋記錄」區域可以查看所有交易
- 使用標籤篩選：全部、代售、代收、待處理
- 點擊「🔄 重整」同步最新資料

## ⌨️ 快捷鍵
- `Ctrl + R` - 重新載入交易記錄
- `Ctrl + T` - 測試 API 連線

## 📂 檔案結構
```
maplestory-artale-trading-system/
├── index.html              # 前端主要檔案 (完整應用)
├── gas-backend.js          # Google Apps Script 後端代碼
├── README.md              # 專案說明文件
└── screenshots/           # 系統截圖 (可選)
```

## 🔧 技術架構

### 前端技術
- **HTML5** - 結構化內容
- **CSS3** - 現代化樣式，支援動畫和響應式設計
- **JavaScript (ES6+)** - 純前端邏輯，無需框架
- **JSONP** - 跨域 API 請求技術

### 後端技術
- **Google Apps Script** - 雲端執行環境
- **Google Sheets API** - 資料儲存和管理
- **RESTful API** - 標準化 API 介面

### 資料結構
```javascript
// 交易記錄格式
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
```

## 🔒 安全性考量

- ✅ 所有資料儲存在你自己的 Google 試算表中
- ✅ API 金鑰和敏感資訊不會暴露在前端
- ✅ 使用 Google 的安全認證機制
- ✅ 支援 HTTPS 加密傳輸

## 🐛 故障排除

### 常見問題

**Q: 顯示「連線測試失敗」**
- 確認 Google Apps Script 已正確部署
- 檢查 API 網址是否正確
- 確認部署權限設為「任何人」

**Q: 提交表單後沒有反應**
- 檢查瀏覽器控制台是否有錯誤訊息
- 確認網路連線正常
- 嘗試重新整理頁面

**Q: 交易記錄顯示空白**
- 確認 Google 試算表 ID 正確
- 檢查試算表是否有資料
- 點擊「重新整理」按鈕

**Q: 手機版介面異常**
- 確保使用現代化瀏覽器
- 嘗試橫向顯示
- 清除瀏覽器快取

### 除錯模式
開啟瀏覽器開發者工具 (F12) 查看詳細錯誤訊息。

## 🛠️ 開發設定

### 本地開發
1. Clone 專案：
   ```bash
   git clone https://github.com/NMAzusa0125/maplestory_ct.git
   cd maplestory_ct
   ```

2. 直接在瀏覽器中開啟 `index.html`

### 修改和自訂

#### 新增委託人
在 `index.html` 中找到以下區塊並新增選項：
```html
<select id="consign-seller" required>
    <option value="">請選擇委託人</option>
    <option value="新用戶">新用戶</option>
    <!-- 在這裡新增更多選項 -->
</select>
```

#### 修改手續費率
在 `gas-backend.js` 中修改手續費計算邏輯：
```javascript
// 在 setRowAutoCalculation 函數中
const feeRateFormula = `=IF(D${rowNumber}="裝備",20%,IF(D${rowNumber}<>"",10%,""))`;
```

#### 新增道具類型
1. 在前端的 select 選項中新增
2. 在後端的 `convertItemTypeToChinese` 函數中新增對應

## 🤝 貢獻指南

歡迎提交 Issue 和 Pull Request！

### 提交 Bug 報告
1. 使用 [Issue 模板](https://github.com/NMAzusa0125/maplestory_ct/issues/new)
2. 提供詳細的錯誤描述和重現步驟
3. 包含瀏覽器版本和環境資訊

### 功能建議
1. 在 Issues 中描述新功能需求
2. 說明使用場景和預期效果
3. 如有可能，提供設計草圖或範例

### 程式碼貢獻
1. Fork 專案
2. 建立功能分支 (`git checkout -b feature/amazing-feature`)
3. 提交變更 (`git commit -m 'Add some amazing feature'`)
4. 推送分支 (`git push origin feature/amazing-feature`)
5. 建立 Pull Request

## 📄 授權條款

本專案採用 MIT 授權條款 - 詳見 [LICENSE](LICENSE) 檔案

## 👥 開發團隊

- **主要開發者** - [Azusa](https://github.com/NMAzusa0125)

## 🙏 致謝

- 感謝楓之谷 Artale 社群的支持
- 感謝所有測試用戶的反饋
- 使用到的開源專案和工具

## 📞 聯絡方式

- **GitHub Issues**: [專案 Issues 頁面](https://github.com/NMAzusa0125/maplestory_ct/issues)
- **Email**: kcazusa1225@gmail.com

## 🔗 相關連結

- [楓之谷 Artale 官網](https://artale.nexon.com/)
- [Google Apps Script 文件](https://developers.google.com/apps-script)
- [Google Sheets API](https://developers.google.com/sheets/api)

---

![GitHub stars](https://img.shields.io/github/stars/NMAzusa0125/maplestory_ct?style=social)
![GitHub forks](https://img.shields.io/github/forks/NMAzusa0125/maplestory_ct?style=social)
![GitHub issues](https://img.shields.io/github/issues/NMAzusa0125/maplestory_ct)
![GitHub license](https://img.shields.io/github/license/NMAzusa0125/maplestory_ct)

**讓楓之谷 Artale 的交易管理變得更簡單！** 🍁