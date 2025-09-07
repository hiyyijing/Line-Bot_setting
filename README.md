# 📒 LINE Bot 記帳教學

---

## ⚙️ 前置作業

### 一、建立 LINE Bot UI

#### 1、 註冊 LINE Developers 帳號

1. 前往 [LINE Developers](https://developers.line.biz/)。
2. 使用 LINE 帳號登入。

📷 *（預留圖片位置：LINE Developers 首頁登入畫面）*

---

#### 2、 建立 **Provider**

1. 在 Providers 點選 `Create` 建立 Provider（名稱可自訂，例如 `記帳Bot`）。
2. 在該 Provider 下建立 **Messaging API Channel**。

📷 *（預留圖片位置：建立 Provider 和 Channel 畫面）*

---

#### 3、 建立 LINE Messaging API Channel

1. 前往 [LINE Developers](https://developers.line.biz/) 並登入。
2. 建立一個 **Provider**（名稱可自訂，例如：「記帳Bot」）。
3. 在該 Provider 下建立 **Messaging API Channel** ，並填入必要資訊：

   * 帳號名稱：自訂（例如：「記帳Bot」）
   * Email：填入有效的電子郵件
   * 公司所在國家或地區：台灣
   * 業種：銀行、保險、金融 銀行、保險、金融（其他）

📷 *（預留圖片位置：建立 Messaging API Channel 詳細畫面）*

---

#### 4、 記帳Bot 帳號設定

1. 進入 Channel 主頁，點選右上角「設定」。

2. 在「回應設定」中：

   * **僅開啟「加入好友的歡迎訊息」**

3. 點選下方 開啟「加入好友的歡迎訊息」設定畫面。

4. 在 「訊息設定」 中：
   編輯歡迎訊息，並儲存變更。範例如下：

   ```
   Hi, {Nickname}
   我是 {AccountName} 🤖
   開始使用請輸入：記帳  
   💰💰💰💰💰
   ```

5. 將「聊天的回應方式」設定為：

   * ✅ 手動聊天 + 自動回應訊息

📷 *（預留圖片位置：回應設定與訊息編輯畫面）*

---

#### 5、 啟用 Messaging API

1. 在「設定」下， 點選下方「Messaging API」。
2. 點選「啟用Messaging API」。
3. 選擇剛建立的 Provider（如：記帳Bot），並按「同意」。
4. 記下 **Channel Secret**（之後會用到）。

📷 *（預留圖片位置：啟用 Messaging API 流程）*

---

#### 6、 取得 Channel API 資訊（‼️很重要）

1. 前往 LINE Developers Console，進入「記帳Bot」的 Channel 頁面。
2. 在 `Basic settings` 可以找到 **Channel Secret**。
3. 在 `Messaging API` 可以找到 **Channel Access Token** ，點選 **Issue** 取得。
4. 複製以下資訊：

   * → Channel Secret
   * → Channel Access Token

 <img src="https://github.com/user-attachments/assets/2f0a364a-d8e2-45e0-8498-3c3de23cef05" alt="LINE Developers Channel 設定畫面" width="500" /> <img src="https://github.com/user-attachments/assets/c83269e3-a574-4746-956b-283f0270fe91" alt="LINE Developers Channel 設定畫面" width="500" />

---

### 二、Google 端設定

### 1、 雲端硬碟 & Google 試算表 設定

1. 在 Google 雲端硬碟建立資料夾，命名為 `linebot`。
2. 建立一份 Google 試算表，命名為 `linebot`。
3. 在試算表中建立三個工作表：

   #### ▸ 工作表一：控制變數

   * 在 `A1` 輸入 `0`（表示狀態）

   #### ▸ 工作表二：帳目資訊

   * 欄位：名稱 / 金額 / 時間 / 類別 / 總金額 / 記帳數目
   * 在「總金額」欄右方輸入公式：

     ```excel
     =SUM(B:B)
     ```
   * 在「記帳數目」欄右方輸入公式：

     ```excel
     =COUNTA(A3:A)
     ```

   #### ▸ 工作表三：帳目類別

   * 輸入自訂分類，範例分類如下：

     1. 飲食
     2. 交通
     3. 購物
     4. ...

📷 *（預留圖片位置：Google 試算表三工作表示意圖）*

---

### 2、 Google Cloud 設定

1. 註冊 Google Cloud 帳號。

2. 前往：控制台 → IAM 與管理 → 服務帳戶 → 建立服務帳戶。

   * 服務帳戶名稱：`linebot`
   * 服務帳戶 ID：`linebot`
   * 點選：建立並繼續 → 完成

3. 建立金鑰：

   * 進入該服務帳戶的「金鑰」頁面。
   * 點選「新增鍵」 → 建立新的金鑰 → 選擇「JSON」。
   * 將 JSON 檔下載後命名為 `linebot.json`，並上傳至 雲端硬碟中 `linebot` 資料夾。

4. 服務帳戶 Email 共用試算表：

   * 在剛建立的 服務帳戶 中， 「詳細資訊」 中的 電子郵件 複製起來。
   * 前往剛建立的 Google 試算表。
   * 點選右上角「共用」。
   * 將該服務帳戶的 email 加入共用，權限設為「編輯」。

5. 啟用 API 權限：

   * 進入 控制台 → API 和服務 → API 程式庫
   * 在 Goole Workspace 下啟用 API：

     *  Google Drive API
     *  Google Sheets API

📷 *（預留圖片位置：建立服務帳戶與金鑰下載畫面）*
📷 *（預留圖片位置：API 啟用畫面）*




---




## ✅ 安裝成功後畫面

<img src="https://github.com/" alt="安裝成功畫面 1" width="500" />

