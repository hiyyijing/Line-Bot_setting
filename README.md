# LINE Bot 記帳 
---

# ⚙️ 前置作業

## 一. 建立 Line Bot UI

### 1. 註冊 LINE Developers 帳號

1. 前往 [LINE Developers](https://developers.line.biz/)。
2. 使用 LINE 帳號登入。

### 2. 建立 **Provider**

1. 在 Providers 點 Create 建立 **Provider**（隨便填寫一個名稱即可）。
2. 在該 Provider 下，建立 **Messaging API Channel**：

### 3. 建立 LINE Messaging API Channel

1. 前往 [LINE Developers](https://developers.line.biz/)。
2. 使用 LINE 帳號登入。
3. 建立一個 **Provider**（名稱隨意，例如「記帳Bot」）。
4. 在該 Provider 下，建立 **Messaging API Channel**：

   * (必填)
   * 帳號名稱：隨意（例如「記帳Bot」）
   * 電子郵件帳號：填寫有效 Email
   * 公司所在國家或地區：台灣
   * 業種：銀行、保險、金融 銀行、保險、金融(其他)

### 3. 記帳Bot 帳號設定

1. 進入主頁，點選右上方 設定。
2. 在 回應設定 中：
   僅開啟「加入好友的歡迎訊息」。
3. 點選下方 開啟「加入好友的歡迎訊息」設定畫面。
4. 在 訊息設定 中：
   編輯想要的訊息，並儲存變更。
   (加入「開始使用請輸入  **記帳**」，ex: 
                                       Hi, {Nickname}
                                       我是{AccountName}🤖
                                       開始使用請輸入  記帳  
                                       💰💰💰💰💰)
5. 將 聊天的回應方式 改為「手動聊天 + 自動回應訊息」。

### 4. 啟用 Messaging API 

1. 在 設定 下， 點選下方 Messaging API。
2. 點選 啟用Messaging API。
3. 選擇剛剛建立的 Provider名稱（記帳Bot) 後按同意。
4. **Channel Secret** 後面會用到先記下來！

### 5. 取得 LINE Channel API (‼️很重要)

1. 前往 LINE Developers Console，點選剛設定的 記帳Bot 進入 Channel 頁面。
2. 在 Basic settings 可以找到 **Channel Secret** 。
3. 在 Messaging API 可以找到 **Channel Access Token** ，點選 Issue 。
4. 複製以下資訊：

   * → Channel Secret 
   * → Channel Access Token 

<img src="https://github.com/user-attachments/assets/2f0a364a-d8e2-45e0-8498-3c3de23cef05" alt="LINE Developers Channel 設定畫面" width="500" />
<img src="https://github.com/user-attachments/assets/c83269e3-a574-4746-956b-283f0270fe91" alt="LINE Developers Channel 設定畫面" width="500" />


---

## 二. Google 端設定

### 1. 雲端硬碟 & Google 試算表 設定

1. 在 Google 雲端硬碟建立資料夾，命名為 linebot。
2. 建立一份 Google 試算表，命名為 linebot。
3. 在 試算表 中建立三個工作表：
   
   * 控制變數：在 A1 輸入 “0” （表示狀態）。
   * 帳目資訊：建立欄位 名稱 / 金額 / 時間 / 類別 / 總金額 / 記帳數目

     ** 在「總金額」右邊輸入公式：
   =SUM(B:B)
     ** 在「記帳數目」右邊輸入公式：
   =COUNTA(A3:A)

   * 帳目類別：輸入自訂分類，例如：
    1. 飲食
    2. 交通
    3. 購物
    ... 


### 2. Google Cloud 設定

1. 註冊 Google Cloud 帳號。
2. 進入 控制台 > IAM 與管理。
3. 在 服務帳戶 中，建立服務帳戶。
4. 服務帳戶名稱 和 服務帳戶ID 填入 linebot， 建立並繼續 > 完成。
5. 在剛建立的 服務帳戶 中， 金鑰 中點選 新增鍵 > 建立新的金鑰，選擇 JSON。
6. 將下載的 JSON 檔命名為 linebot.json ，並上傳至 雲端硬碟 中的 linebot 資料夾。
7. 在剛建立的 服務帳戶 中， 詳細資訊 中的 電子郵件 複製起來。
8. 開啟 Google 試算表 的 共用 ，將服務帳號的 電子郵件 加到共用 ，並給予 編輯權限。
9. 進入 控制台 > API 和服務 > API 程式庫。
10. 在 Goole Workspace 下開啟 API 權限：啟用 Goole  Drive API 和 Goole Sheets API 權限。

---




## ✅ 安裝成功後畫面

<img src="https://github.com/" alt="安裝成功畫面 1" width="500" />



