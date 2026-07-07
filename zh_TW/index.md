# Apnea Comp — 使用者手冊

**AIDA Competition Management System**

本手冊涵蓋使用 Apnea Comp 運營一場自由潛水比賽的全過程，從設定到結果。應用程式內的 Help（More → Help）是快速參考；本文件更為深入，包含運營情境與疑難排解。

如果你只有五分鐘，請閱讀下面的 **快速開始** 以及底部的 FAQ。

---

## 目錄

1. [開始之前](#開始之前)
2. [快速開始](#快速開始)
3. [角色及其權限](#角色及其權限)
4. [建立賽事（Organizer）](#建立賽事organizer)
5. [加入賽事（Staff）](#加入賽事staff)
6. [以選手身分加入](#以選手身分加入)
7. [Setup：選手、Line 與 OT](#setup選手line-與-ot)
8. [Break Times](#break-times)
9. [團隊賽（Team）](#團隊賽team)
10. [Check-in](#check-in)
11. [Start List & Speaker Mode](#start-list--speaker-mode)
12. [輸入判定結果](#輸入判定結果)
13. [罰分（Rulebook 17.8）](#罰分rulebook-178)
14. [Protests（申訴）](#protests申訴)
15. [Re-swim & Opener](#re-swim--opener)
16. [日程調整（OT Delay）](#日程調整ot-delay)
17. [推播通知](#推播通知)
18. [離線運作](#離線運作)
19. [AIDA 整合](#aida-整合)
20. [多日賽事](#多日賽事)
21. [結果與匯出](#結果與匯出)
22. [顯示 & 語言](#顯示--語言)
23. [FAQ](#faq)
24. [疑難排解](#疑難排解)
25. [隱私與資料](#隱私與資料)
26. [聯絡方式](#聯絡方式)

---

## 開始之前

你將需要：

- 一部安裝了 Apnea Comp 應用程式的 iPhone 或 Android 裝置。
- 穩定的網路連線（比賽當天為選用 — 參見 [離線運作](#離線運作)）。
- 如果賽事將進行正式計分，需要 AIDA International 帳號（僅 Organizer）。
- 對於 Organizer：該比賽的 AIDA Token 與 Event ID。沒有它們，應用程式將以 🧪 Mock mode 運作（範例資料，無 AIDA 同步）。

我們建議每位裁判 / 工作人員使用自己的裝置。應用程式支援多人同時在同一賽事中作業 — 結果會在裝置之間即時同步。

---

## 快速開始

### 面向 Organizer（賽事建立者）

1. 開啟應用程式，在 Events 畫面點按 **+**。
2. 輸入賽事名稱、類型（Pool / Depth / Team）、日期，然後點按 Create。
3. 開啟賽事 → **Edit Event** → 貼上 **AIDA Token** 與 **AIDA Event ID** → 點按 **Test Connection** → Save。
4. Setup 分頁 → **Load Athletes** 從 AIDA 拉取開始名單。
5. Setup 分頁 → 設定 **Lines**（水道數量）、**First OT** 與選手之間的 **Interval**。
6. 將（在 Edit Event 中可見的）賽事 **invite code** 分享給你的工作人員。
7. 工作人員加入時在 **Users** 分頁中核准他們（他們會顯示為 Pending）。

### 面向 Staff（裁判、報到人員等）

1. 開啟應用程式，登入。  
   *提示：勾選 **Remember email** 可在下次預先填入你的電子郵件。你也可以勾選 **Remember password** — 此時密碼會儲存在裝置的安全金鑰庫中（iOS Keychain / Android EncryptedSharedPreferences），絕不會儲存在我們的伺服器上。登出會同時清除兩者。*
2. Events 畫面 → 點按 **Join with code** → 貼上 invite code。
3. 在 Organizer 核准你並指派角色（Judge、Main Judge、Staff 等）之前，你會顯示為 Pending。

### 面向選手

1. 開啟應用程式，用你的電子郵件註冊。
2. 註冊時選擇 **I am an athlete**。
3. 應用程式會嘗試自動將你的姓名與 AIDA 的開始名單比對。
4. 如果比對成功，你註冊的賽事會立即出現。如果你的姓名有同名，請向 Organizer 索取一次性 invite code。

現在你已準備好運營當天的比賽。

---

## 角色及其權限

| 角色 | Setup | Judge | Check-in | Users | Log | OT Delay | Send Push |
|------|-------|-------|----------|-------|-----|----------|-----------|
| 👑 Organizer | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ⚖️ Main Judge | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ✏️ Judge | — | ✅ | ✅ | — | — | — | — |
| 👀 Staff | — | 檢視 | ✅ | — | — | — | — |
| 🏊 Athlete | — | — | — | — | — | — | — |
| ⏳ Pending | — | — | — | — | — | — | — |

- **Organizer** 是建立賽事者的預設角色。
- **Main Judge** 擁有與 Organizer 相同的權限；在 Users 中指派。
- **Athlete** 為唯讀 — 僅開始名單與個人結果。無法存取其他成員的資料、AIDA token 或控制功能。
- **Pending** 成員需等待 Organizer 或 Main Judge 在 Users 中核准並指派真正的角色。

---

## 建立賽事（Organizer）

### 基本資訊

- **Name** — 對你的工作人員可見。
- **Type** — 🏊 Pool、🌊 Depth 或 👥 Team。
- **Dates** — 對於多日賽事，選擇開始與結束日期。

### AIDA 整合（建議）

開啟賽事 → **Edit Event** → 填寫：

- **AIDA Token** — 來自你的 AIDA 管理面板。
- **AIDA Event ID** — AIDA 比賽的數字 ID。

點按 **Test Connection**。綠色勾號表示憑證有效，應用程式可以讀取開始名單。Save。

> ![帶有 AIDA 欄位的 Edit Event 畫面](../images/edit-event-aida.png)

如果你將這些留空，或將 token 設為 `test` 或 `demo`，應用程式將以 🧪 **Mock mode** 運作 — 它會產生用於練習的範例選手。Mock mode 不會向 AIDA 傳送任何內容。

### 邀請你的工作人員

invite code 顯示在 **Edit Event** 中。透過你常用的管道（聊天、電子郵件、紙張）分享它。工作人員在 Events 畫面使用 **Join with code** 輸入該代碼。

> 提示：尚不支援輪換 invite code。請像對待密碼一樣對待它，只與應該加入團隊的人分享。

---

## 加入賽事（Staff）

1. 登入應用程式。
2. 在 Events 畫面，點按 **Join with code**。
3. 貼上代碼。賽事會以 **Pending** 狀態出現在你的清單中。
4. 等待 Organizer 核准你並指派角色。核准後你會看到賽事變為可點按。

如果你不小心用錯了代碼，請讓 Organizer 在 Users 中移除你，以便重新嘗試。

---

## 以選手身分加入

如果你是參賽而不是運營賽事，請以選手身分註冊，以檢視你的開始名單、OT、line 與個人結果。

你可以隨時在工作人員檢視與選手檢視之間切換：點按你的頭像（右上角）→ **Switch to Athlete Mode**（返回時用同樣的方法）。

### 運作原理

當你註冊時，應用程式會讀取你的姓名，並嘗試將其與 organizer 已從 AIDA 載入應用程式中的選手進行比對。如果恰好找到一個比對項，你的帳號會自動連結。否則，organizer 可以簽發一次性 invite code。

### Path A — 自動比對（大多數情況）

1. 用你的電子郵件註冊。
2. 選擇 **I am an athlete**。
3. 完全按照在 AIDA 註冊的內容輸入你的 **first name**、**last name**、**gender** 與 **nationality**。
4. 應用程式搜尋已載入的賽事。如果你的姓名與單一選手相符，且 gender / nationality 一致，你會立即被連結。
5. Events 畫面現在會顯示你所出現的賽事。點按其中一個即可檢視你的開始名單以及（之後的）結果。

### Path B — invite code（當姓名衝突時）

如果兩名選手同名，自動比對無法判斷哪一個是你。請向 Organizer 索取 invite code：

1. Organizer 開啟賽事 → **Athlete Invite Codes** → 在清單中找到你的姓名 → 點按它產生一個 6 字元代碼。
2. Organizer 私下將代碼傳送給你。
3. 你開啟應用程式 → Events → **Enter invite code** → 貼上它。
4. 應用程式驗證代碼並連結你的帳號。

### broadcast（啟用）碼 — 最快的加入方式

Organizer 可以開啟一組 **broadcast 碼**（顯示為 **Athlete code**），任何選手都能用它直接加入賽事 — 在尚無 AIDA start list，或選手不在名單上時很有用。

**Organizer：** 開啟賽事 → **Setup** → 點按 *Athlete code* 旁的綠色 **+** 來產生它，然後 **複製** 並分享（聊天、紙張、投影）。隨時點按電源圖示即可關閉。

**選手：** 開啟應用程式 → Events → **Enter code** → 貼上 broadcast 碼。加入後你即可檢視 start list 與結果，並提交你的文件。

> ![Setup — Athlete (broadcast) code](../images/broadcast-code.png)

### Find me on AIDA

> ![Find me on AIDA 搜尋](../images/aida-find-me.png)

如果自動比對沒有找到你，你可以手動連結你的 AIDA 選手檔案。在 **Edit Profile** 或 **Athlete Setup** 中，點按 **Find me on AIDA**，輸入你的姓名，並從結果中選擇你的檔案。這會儲存你的 AIDA athlete ID，使你的結果正確比對。🔄 sync 圖示還會拉取你註冊的賽事。（沒有比賽歷史的選手可能不會出現在搜尋中 — 這種情況下，請完全按照在 AIDA 註冊的內容手動輸入你的姓名、nationality 與 gender。）

### 你能看到什麼

Athlete Mode 有四個分頁：**My Info**、**Start List**、**Results** 與 **Rewards**（過往賽事顯示三個 — 無 Start List）。

- 🏊 Athlete 角色：對你所出現的賽事的唯讀存取。
- **My Info** — 你被指派的 OT、line、check-in 狀態（Pending / Checked-in / DNS / Late）以及你的結果。你也可以在這裡提交申訴（參見 [Protests](#protests申訴)）。
- **Start List** — 當天的進行順序，附有「Show my line only」篩選。
- **Results** — 已發布的結果。
- **Rewards** — 依 discipline 與 gender 排列的積分排名，你的列會被醒目標示。

你無法看到其他選手的個人資訊、裁判的筆記或 AIDA token。

### 推播通知

如果你允許通知，你會收到：

- **Start list published** — 當 Organizer 發布當天的開始名單時。
- **Unofficial / Official results** — 當結果發布時。
- **OT delay** — 如果日程變動且你的 OT 改變時。
- **Check-in 截止提醒** — 自動傳送，僅當你尚未報到時：
  - check-in 截止（即 OT − 1h）前 1 小時
  - check-in 截止前 30 分鐘
- **Protest 更新** — 如果有關於你的 protest 被代為提交（要求你簽名），或被 jury 裁決時。

通知文字會以你選擇的應用程式語言送達。你可以隨時在裝置的系統設定或應用程式的 About 畫面中關閉通知。

---

## Documents (同意書)

許多賽事要求選手在參賽前提交 AIDA 同意書。開啟 **My Info → Documents**。

- **必填表單** — Competition Entry、Image Rights 同意書和 Liability 免責聲明。**Medical Statement** 為選填項，但通常會被要求。
- **兩種提交方式** — *在應用程式內填寫*（輸入各欄位並在螢幕上簽名，系統會為你產生 PDF），或*上傳*已簽名的紙本副本*照片*。
- **Medical Statement** — 自簽發之日起一年內有效。將其儲存到個人資料中（Edit Profile → Medical Statement），即可在多個賽事中重複使用。如果上傳照片，請輸入證書上顯示的簽發日期。簽發日期*之後*發生的壓力性損傷或昏厥會使證書失效——請重新提交一份。
- **截止時間** — 如果到賽事前一天仍缺少必填表單，你會收到一則列出缺漏項目的推播提醒。

**給工作人員 (Organizer / Main Judge):** 開啟 **More → Documents**，可查看每位選手的提交狀態、開啟檔案，並**將全部內容下載為 ZIP**（依文件類型分資料夾）。當選手申報受傷或昏厥時，該 medical statement 會被標記為**人工核驗**——當面確認證書後，點按 *Mark verified*。已提交的文件在賽事結束後保留 15 天，之後刪除。

---

![Athlete — My Info → Documents](../images/documents-athlete-list.png)

![Fill in app and sign](../images/documents-fill-sign.png)

![Medical Statement saved on profile](../images/documents-medical-profile.png)

![Staff — Documents status & manual-check](../images/documents-staff-status.png)

![Staff — verify medical statement](../images/documents-staff-verify.png)

## Setup：選手、Line 與 OT

> ![Setup 畫面版面](../images/setup-screen.png)

Setup 是你決定當天日程的地方：每位選手在哪條 line 游泳、他們的 OT（official time）是什麼時候，以及當天有哪些休息。

**自動儲存** — 你在 Setup 中所做的每項變更都會自動儲存到伺服器。如果你離開應用程式再回來，你的設定會被還原。如果共同 organizer 從 AIDA 重新載入選手，日程仍會遵循你的 line 配置。

### 載入選手

- **Load Athletes** — 從 AIDA 拉取已註冊的開始名單。冪等：重新載入時現有的判定會被保留。
- **Mock mode** — 產生用於練習的範例開始名單。

### 設定 Line 與 OT（基本）

- **Lines** — 水道數量（Pool）或平台 line 數量（Depth）。
- **First OT** — 第一位選手開始的時間（例如 `09:00`）。
- **Interval** — 同一條 line 上相鄰選手之間的間隔。
- **Depth Line Interval**（僅 Depth / Team） — 當 **ON** 時，各 line 依序進行：每條 line 以錯開的偏移量開始（Line 1，然後幾分鐘後 Line 2 …），且 Start List 會顯示每條 line 的倒數計時。該偏移量必須滿足 `(lines − 1) × line_interval < athlete_interval`，否則無法產生日程。當 **OFF** 時，所有 line **並行** 進行 — 同一列的選手共享相同的 OT，與 Pool 模式完全一樣。

### Advanced Setup（選用，可折疊）

> ![Advanced Setup 折疊](../images/setup-advanced-collapsed.png)
> ![Advanced Setup 展開](../images/setup-advanced-expanded.png)

點按 **Advanced Setup** 可展開更多選項以進行精細控制：

- **依 discipline 設定 line（僅 Pool）** — 為每個 discipline 指派不同數量的水道。例如，STA 使用 4 條水道，但 DYN/DNF 僅使用 2 條水道。應用程式會為每個 discipline 產生獨立的子日程，並將它們拼接在一起。
- **跨 discipline 的水道延續** — 當上一個 discipline 在 line 中途結束（例如 STA 在 4 條水道中的第 3 條結束）時，下一個 discipline 既可以從水道 1 重新開始（預設），也可以從水道 4 繼續。當裁判在不同 discipline 之間留在同一條水道時很有用。

- **Custom Intervals（單獨設定間隔）** — 在基本間隔之外，依出發順序號區間設定不同間隔。例如：#1–#10 → 10 分鐘，#11–#20 → 8 分鐘，#21–#30 → 7 分鐘。點按 **Add interval（新增間隔）** → 設定 *起始順序 / 結束順序 / 間隔* → **Done**。OT 會自動重新計算並儲存。此為按日設定；區間不可重疊且需在選手數以內；沒有區間則全部套用基本間隔。若當天存在手動休息，則跳過 OT 重算（與 Save Configuration 相同 — 保護手動調整的 OT）。

### Line 指派

載入選手後，開啟 **Assign Lines** 在 line 之間移動並重新排序。OT 會自動重新計算：

- Pool：輪流指派，OT 取決於在 line 內的位置。
- Depth：含 line 循環的完整序列，並考慮 depth line interval 規則。

**直接 line 指派** — 對於特殊情況（例如為國家紀錄嘗試保留某條特定 line，或放置 re-swim — 參見 [Re-swim & Opener](#re-swim--opener)），點按一位選手，然後點按目標 line 與位置。日程會重新排布以遵循你的選擇。

完成後 Save — 當天的開始時間至此確定。

---

## Break Times

休息會讓日程暫停一個固定的時間段。應用程式支援兩種休息。

### Time-based 休息（Lunch Break 等）

> ![Setup 中的 Time-based 休息](../images/break-time-based.png)

用於所有人事先約定好的固定時間休息（午餐、頒獎典禮等）：

1. 開啟 Setup → **BREAK TIMES** → **Add Break Time**。
2. 選擇 **Time-based**。
3. 輸入開始時間與結束時間（例如 `12:00` – `13:00`）。
4. 儲存。

任何 OT 落在休息時間段內的選手都會被往後推，使其 OT 落在休息結束之後。水道指派會被保留。

### After Athlete 休息（Build 48 新增）

> ![正在新增的 After Athlete 休息](../images/break-after-athlete-add.png)
> ![已列出的 After Athlete 休息](../images/break-after-athlete-listed.png)

當你需要在 **某位特定選手完成之後** 插入休息時使用，與時鐘時間無關。典型情境：熱身選手結束後，你希望在正式選手開始前有 60 分鐘的休息。

1. 開啟 Setup → **BREAK TIMES** → **Add Break Time**。
2. 選擇 **After Athlete**。
3. 選擇標誌該段結束的選手。
4. 輸入休息時長（例如 `60` 分鐘）。
5. 儲存。

被選中的選手以及 **開始名單順序中其後的每一位選手** 都會被延後該休息時長。其他 discipline（順序在前、即便時鐘時間相同的選手）不受影響。水道指派會被保留。

要移除某個休息，點按 BREAK TIMES 清單中它旁邊的 🗑️ 垃圾桶圖示。

---

## 團隊賽（Team）

Team 類型的賽事（賽事類型 **Team**）將選手分入各隊伍，由隊伍的合計分數決定名次。**Setup** 中會出現一個 **Teams** 區塊 — 僅針對 Team 類型的賽事。

> ![Setup 中的 Teams 區塊](../images/team-setup.png)

### 建立與編輯隊伍

點按 **New Team** 開啟隊伍編輯器。

> ![隊伍編輯器 — 名稱、顏色、成員](../images/team-edit.png)

- **名稱** — 必填。
- **顏色** — 選一個顏色，便於在清單中辨認隊伍。
- **成員** — 勾選屬於該隊伍的選手。清單可按姓名或 nationality 搜尋。選擇一位已在其他隊伍中的選手，會將其移動過來。

每張隊伍卡片都會顯示其名稱、顏色與成員數。點按卡片可 **編輯**，或使用其選單 **刪除** 它。

> 在多日出場的選手只會顯示一次 — 選擇該選手會將其 **所有日的項目** 都指派給該隊伍，因此每個人只需挑選一次。

---

## Check-in

選手在熱身前報到。開啟 **Check-in** 分頁。

- 點按一張處於 pending 狀態的選手卡片，開啟簽名表。
- 選手在螢幕上簽名，點按 **Save** → 該選手以目前時間被標記為 Checked In。卡片隨後會同時顯示 OT 與報到時間。
- 對於缺席者：點按選手 → 確認 **DNS**（Did Not Show）。
- 對於超過截止時間的遲到者：點按 → **Late Check-in**。他們會自動取得帶「Late Check-in」remark 的 Red 卡。
- **自動 Late Check-in** — 在 check-in 截止（OT − 1h）過後仍處於 pending 的選手會被自動標記為 **Late Check-in**。pending 清單會以 `Check-in HH:mm` 顯示每位選手的截止時間。
- **AIDA 同步** — DNS 與 Late Check-in 會像判定結果一樣自動提交到 AIDA（作為 Red 卡 / 0 分）。你不再需要在 Judge 中手動輸入這些。
- 點按頂部的迷你卡片（In / Late / DNS / Pending）可將清單篩選為該組。

> 簽名繪製僅用於視覺確認 — 它在報到那一刻向工作人員顯示，並在表單關閉後立即被捨棄。我們不會在任何地方儲存簽名影像（既不在伺服器上，也不在裝置上）。僅記錄已擷取簽名這一事實，以及報到時間。

> Check-in 也可離線運作。如果你在確認時裝置處於離線狀態，報到會被保留在裝置記憶體中，卡片上帶有一個小的 ⛔「Offline」徽章，並在重新連線後 5 秒內自動同步到伺服器。參見 [離線運作](#離線運作)。

---

## Start List & Speaker Mode

> ![帶倒數計時的 Start List 畫面](../images/start-list-countdown.png)

Start List 分頁顯示當天的進行順序，以及距下一位選手 OT 的即時倒數計時。每個 OT 臨近時，應用程式會朗讀倒數計時，使選手與裁判無需盯著螢幕即可聽到。

### 語音倒數計時

每個 OT 臨近時，應用程式會播放語音提示，使選手與裁判無需盯著螢幕即可聽到讀數。這些提示是 **預先錄製的音訊檔案**，因此在 **iOS 與 Android 上聽起來完全相同**（早期版本使用每部手機內建的 text-to-speech，各裝置之間有所不同）。

OT 之前的提示：
`2:00`（「two minutes to official top」）、`1:30`、`1:00`、`0:30`、`0:20`、`0:10`，然後 `5 — 4 — 3 — 2 — 1`，並在 OT 時：**「official top」**。

出發視窗期間（OT 之後）的提示：在 +1 秒時 **「plus one」**，隨後隨著視窗走完會報出經過的秒數 — 直到該 discipline 的上限 — 如果選手在視窗結束前仍未出發，則以 **「start cancelled」** 結束。

### 語音提示（Announce）

除了自動的倒數計時提示，Start List 還有一個 **Announce（語音提示）** 按鈕，可手動觸發一次語音提醒。點按它，輸入 OT 之前的分鐘數，裝置便會朗讀「N minutes to Official Top」。

這與自動的語音倒數計時佇列各自獨立 — 它是由你按需觸發的一次性提示。語音會依裝置語言（en / ko / ja / zh / zh_TW）發聲。

### 靜音按鈕

> ![Start List 上的靜音切換](../images/start-list-mute.png)

點按 AppBar 中的 🔊 / 🔇 圖示可切換語音播報。在以下情況很有用：

- 你在一個已有獨立 PA 系統播報的室內泳池中運營。
- 選手更喜歡無聲倒數計時。
- 你臨時進入會議，需要讓裝置安靜下來。

靜音只對你切換它的那台裝置生效 — 同一賽事中的其他裝置會繼續播報。無論如何，視覺倒數計時都會繼續運行。

### Speaker Mode

> ![Speaker Mode 已啟用](../images/speaker-mode.png)

Speaker Mode 將裝置變成一個 **專用倒數計時播報器** — 非常適合場館的主喇叭。一旦啟用：

- 螢幕被鎖定在 Start List 檢視；其他分頁被隱藏。
- 靜音被強制關閉（不會被意外靜音）。
- 螢幕保持常亮（無自動鎖定）。
- 退出 Speaker Mode 需要 PIN，因此好奇的旁觀者不會意外關閉它。

**要啟用**：開啟角色 / 個人檔案選單 → **Speaker Mode** → 設定一個 4 位 PIN。

**要退出**：點按 Speaker Mode 徽章 → 輸入 PIN → 確認。

#### 背景語音播放

在 Speaker Mode 中，語音（倒數計時佇列與 Announce 提示）即使在應用程式被切到背景或螢幕被鎖定時也會 **持續播放**。iOS 會維持一條無聲的 keep-alive 音軌，Android 則使用一則前景服務通知（「Start list countdown active」）。如此一來，即使手機已鎖定，場館的主喇叭仍會持續播報。此行為僅限 Speaker Mode。

建議設定：將一部專用手機或平板插入場館的音響系統，並在整個比賽日保持 Speaker Mode。讓它一直接著充電器 — 語音播放比被動閒置更快耗電。

### 螢幕常亮

應用程式會在 **每一個** 畫面上保持螢幕常亮，而不僅僅是 Start List，因此即使你不觸碰裝置，倒數計時與通知也能運作。這是一個全域設定 — 你一開啟應用程式它就生效。注意：對於整天賽事，請讓裝置一直接著充電器；電量會比平常消耗得更快。

---

## 輸入判定結果

> ![帶有選手卡片的 Judge 分頁](../images/judge-tab.png)

Judge 分頁顯示當天的所有選手。點按一張卡片以輸入結果。

### 輸入結果

1. **RP** — 實際表現（static 為時間，dynamic 為距離，depth 為深度）。
2. **卡片** — White（乾淨）、Yellow（罰分）或 Red（DQ）。
3. **罰分原因** — 選擇 White 以外的卡片時必填。參見 [罰分](#罰分rulebook-178)。
4. **Start offset** — 提前（負數）或延遲（正數）的秒數。用於出發視窗罰分的計算。
5. **REMARKS** — 對於某些原因（BO、Other Penalty、DQ Other 等）必填。應用程式會預填一個範本；請補全缺漏的細節。
6. 點按 **Save Result**。

### 卡片徽章

儲存後，你會在選手卡片上看到一個小徽章：

- **✅ AIDA** — 已同步到 AIDA International。
- **🔁 Retry** — 同步到 AIDA 失敗；點按可查看原因並重試。
- **⛔ Offline** — 已在此裝置上本機儲存；恢復連線後將自動同步。參見 [離線運作](#離線運作)。

如果未顯示徽章，則表示未設定 AIDA 整合（該選手沒有 startId）— 在 Mock mode 中這是正常的。

### Judge Calculator

對於 Pool 的 discipline，應用程式內建了計算器，可幫你從原始量測值算出 RP，而無須心算。計算器位於 Judge 分頁 → 選手詳情表中，僅在相關的 discipline 才會出現。

#### Pool Length

在使用 Distance Calc 之前，必須先設定 **Pool Length（m）**。在賽事 **Setup** 中設定它 — 僅 Pool 與 Team 類型的賽事可用（Depth 不適用）。如果未設定 pool length，dynamic 的距離計算器將無法換算 lap 數。

#### Distance Calc（DYN / DYNB / DNF）

對於 dynamic 的 discipline，點按選手詳情表中的 📏 尺（ruler）按鈕。輸入完成的 **完整 lap 數**，再加上最後的 **部分距離（m）**。結果為 `lap 數 × Pool Length + 部分距離`。點按 **Fill RP** 即可將算得的距離自動填入 RP 欄位。

#### STA Average Calc（STA）

對於 STA，點按 ⏱ 計時器按鈕。輸入兩位裁判各自量測的時間（mm:ss）。應用程式會取兩者的平均（四捨五入到最接近的秒），再以 **Fill RP** 將其填入 RP。

#### 注意事項

- 如果算得的 **RP 小於 AP**，White 卡會自動停用 — 表現不及 AP 不能給 White。
- Depth 的 discipline（CWT / CWTB / FIM / CNF）沒有計算器 — 請手動輸入 RP。

---

## 罰分（Rulebook 17.8）

應用程式遵循 AIDA Rulebook 第 17.8 節。原因依卡片顏色分組。

### 🟨 Yellow 卡原因

- **Start** — 不正確的出發技術（Pool DYN：牆壁出發失敗等）。
- **Early Start** — 在 OT 之前出發。在出發視窗內，每提前 5 秒罰 1 分。
- **Late Start** — 在 OT 之後出發。在出發視窗內，每延遲 5 秒罰 1 分。
- **Grab** — 在表現過程中拉拽了 line、牆壁或平台。
- **Other Penalty** — 未涵蓋的其他任何情況。**REMARKS 必填**。

### 🟥 Red 卡原因

- **Surface Protocol** — 出水 15 秒內的 surface protocol 不正確。
- **Blackout Surface** — 在水面失去運動控制或意識。**REMARKS 必填**（恢復時間等）。
- **Blackout UW** — 水下黑視。**REMARKS 必填**。
- **DQ Late Start** — Late Start 超過出發視窗（Pool +10s、Depth +30s）。
- **Jump Start** *(僅 Pool DYN)* — 在 OT 之前離開牆壁。
- **DQ Other** — 因任何其他原因取消資格。**REMARKS 必填**。

### 出發視窗

| Discipline | 視窗 | 視窗內 | 超過視窗 |
|------------|--------|----------------|-------------|
| Pool | ±10 s | 每 5 秒 1 分（Yellow Early/Late Start） | 延遲一側為 DQ Late Start（Red）；提前的 Pool 牆壁出發為 Jump Start（Red，僅 DYN） |
| Depth | ±30 s | 每 5 秒 1 分（Yellow Early/Late Start） | 延遲一側為 DQ Late Start（Red） |

### REMARKS

AIDA Rulebook 4.1.16.2 要求為每個 Yellow 與 Red 提供書面原因。如果某原因要求填寫 REMARKS 而它為空，Save 按鈕會封鎖該操作。

當你選擇一個原因時，REMARKS 欄位會預填一個範本（例如 `BO Surface, recovery: ___`）。儲存前請補全缺漏的細節 — 這是正式紀錄。

### 多選與組合卡

> ![Red 卡多選表](../images/judge-red-multi-select.png)

當你點按 Red 卡時，原因表會以兩個分組同時顯示 **Red 與 Yellow** 兩類原因：

- **DQ Reason (Red)** — Surface Protocol、Blackout Surface、Blackout UW、Airways、DQ Late Start、Jump Start、Pull、Touch、Other Lane、Check-in DQ、DQ Other
- **Additional Penalty (Yellow)** — Under AP、No Tag、Grab、Pull、Turn、Start、Early Start、Late Start、Lanyard、Other Penalty

你可以在一次儲存中跨兩個分組選擇多個原因 — 例如 Red **Airways** 加上 Yellow **Under AP**。所選的標籤依類別以顏色區分，因此你可以一眼看出正在記錄什麼。

Yellow 卡單獨也支援多選（例如 Early Start + Grab）。Yellow 卡不會顯示 Red 分組。

---

## Protests（申訴）

protest 是根據 AIDA Rulebook 17.8 提出的對某一結果的正式異議。Apnea Comp 會追蹤整個流程 — 提交、選手的簽名、jury 的裁決，以及對結果的任何變更。

**每個 protest 都以選手的簽名結束**，即使是工作人員代選手發起的也是如此。

### 誰可以提交

Organizer、Main Judge、Judge 或選手本人。應用程式不追蹤費用。

### 以選手身分提交

> ![選手提交 protest](../images/protest-file.png)

1. Athlete Mode → **My Info** → 點按你結果旁邊的 **File Protest**。
2. 輸入原因，在螢幕上簽名，然後提交。

> ![protest 簽名板](../images/protest-sign.png)

protest 狀態變為 **Pending** — 等待 jury。

### 代為提交（工作人員）

1. **Judge** 分頁 → 點按一張選手卡片 → **File Protest (on behalf)**。
2. 輸入原因並提交。此時尚無簽名。
3. protest 會以 **Awaiting signature** 狀態傳送給選手。選手在自己的手機上開啟 **My Info**，查看後簽名 — 只有這樣它才會變為 **Pending**。

### Jury 裁決

> ![protest 清單](../images/protest-list.png)

開啟 **More → Protests**（Organizer / Main Judge / Judge）。清單依狀態對 protest 分組（Awaiting signature / Pending / Reviewing / Accepted / Rejected / Withdrawn）。點按其中一個進行裁決。

> ![protest 裁決畫面](../images/protest-decide.png)

- **Accept** — 你可以修改結果（card、RP、remarks）。選手的紀錄會自動更新，變更會流轉到 Results、Rewards 與 AIDA。
- **Reject** / **Withdraw** — 結果維持不變。

當 protest 仍處於 **Awaiting signature** 時無法裁決 — 選手必須先簽名。

### Jury 投票

裁決可採用 **匿名 jury 投票**：Judge 與 Main Judge 各自投下 **Accept** 或 **Reject**。投票是匿名的 — 不會顯示誰投了什麼，只顯示各自的票數合計。

如果票數相同，由 **Main Judge** 投出決定性（deciding）的一票來定案。最終的裁決表單需要 **Jury 簽名** 才能完成。

### 刪除 protest

Organizer 或 Main Judge 可以從其詳情畫面（🗑 垃圾桶圖示）刪除任何 protest — 用它來清除測試項目，或清除卡在等待一個永遠不會到來的簽名上的舊有 protest。

### 通知

當 protest 被 **提交**、**等待簽名** 或 **裁決** 時，所有工作人員與相關選手都會以各自選擇的應用程式語言收到推播。

---

## Re-swim & Opener

### Re-swim

當 protest 被接受（或裁判要求重新表現）時，選手會再游一次。由於從 AIDA 載入某日的開始名單會取代當日的選手，re-swim 會先 **在佇列中預留**，然後在建構目標日的名單時插入 — 這樣它就絕不會被重新載入抹除。

> ![預留 re-swim — 選擇日期](../images/reswim-reserve.png)

1. **預留** — Judge / Main Judge / Organizer。在裁決 protest 時核准 re-swim，或為所選日期預留它（從日期下拉選單中選擇日期）。
2. **放置** — 當建構或載入該日的開始名單時，應用程式會提示：*「N re-swim(s) to place.」*。選擇一種自動排序（AP 遞增 / 遞減 / 隨機），或用 **Assign Lines** 手動放置每位選手（點按選手，然後點按目標 line 與位置）。如果 re-swim 在已載入的那一天，你可以立即放置它；否則，在 Setup → Add Athlete 下方有一個 **「Place pending re-swims」** 安全按鈕。

> ![將 re-swim 放入開始名單](../images/reswim-placement.png)

3. **原項目被排除** — 原項目會被標記為 **invalidated**：從排名（Rewards）中排除，但仍顯示在 Results 中。re-swim 的結果計入當日排名，並使用原始 start ID 推送到 AIDA。

### Opener

**opener** 是一個不應計入的熱身或示範項目。Organizer / Main Judge 在 **Setup → Add Athlete** 下新增一個：姓名、nationality、gender、discipline、AP、PB（STA 使用 mm:ss 時間選擇器；其他 discipline 使用數字）。Opener **被排除在排名之外，且絕不會傳送到 AIDA**。

> ![Add Athlete 對話框（opener / 手動新增）](../images/add-athlete.png)

---

## 日程調整（OT Delay）

如果當天進度落後（熱身過長、發生意外、設備問題），你可以在不重建開始名單的情況下推移剩餘的 OT。

### 在哪裡找到它

在 **Start List** 或 **Judge** 分頁中，AppBar 右側的角色徽章前會顯示一個 🕒 圖示。**僅對 Organizer 與 Main Judge 可見。**

> ![OT Delay 圖示位置](../images/ot-delay-icon.png)

### 如何使用

1. 點按 🕒 → **Adjust Schedule** 對話框開啟。
2. 選擇延遲的起點選手（OT 開始推移的第一位）。
3. 以 **分鐘** 輸入延遲（整分鐘，僅正數）。
4. 預覽會顯示新的時間 — 每位受影響選手的 舊 → 新。
5. 點按 **Apply**。

從所選選手起的每個 OT 都會往前推移該數值。對應的 check-in / 熱身時間也會一起推移。

### 副作用

- **推播通知** — 每位 OT 發生變化的選手都會收到自動推播：*「Your OT has been delayed by N minute(s)」*。他們無需訂閱任何東西；通知僅針對受影響的選手定向傳送。
- **活動紀錄** — 記錄在 Log 畫面中。

### 重要

- 僅支援正向延遲。無法提前。
- Undo **尚不可用** — 套用前請仔細查看預覽。
- 所有工作人員的裝置都會即時更新。

---

## 推播通知

Apnea Comp 使用推播通知來傳送對時間敏感的賽事更新。通知透過 OneSignal 投遞，OneSignal 再將其轉發到 APNs（iOS）與 Firebase Cloud Messaging（FCM，Android）。每則通知都以接收者選擇的應用程式語言傳送。

### 會傳送什麼

有兩種：你手動觸發的通知，以及系統根據賽事狀態自動傳送的通知。

#### 手動（僅 Organizer / Main Judge）

從 More 選單中，**Send Push** 會開啟一個帶三個按鈕的小面板。每個都傳送給所選日期已註冊的所有選手：

- **Publish Start List** — 當當天的水道與 OT 確定時。
- **Unofficial Results** — 發布初步結果供選手查看。
- **Official Results** — protest 視窗結束後的最終結果。

每次點按都會顯示一個確認對話框，在傳送前列出接收者數量。

#### 自動

這些無需工作人員操作即可執行：

| 觸發 | 接收者 | 時機 |
|---------|-----------|------|
| OT Delay 已套用 | 僅受影響的選手 | Organizer / Main Judge 套用延遲後立即 |
| Check-in 截止提醒（1 小時） | 尚未報到的選手 | OT 前 2 小時（= check-in 截止前 1 小時） |
| Check-in 截止提醒（30 分鐘） | 尚未報到的選手 | OT 前 1.5 小時（= check-in 截止前 30 分鐘） |
| Protest 提交 | 所有賽事工作人員 + 該選手 | 當 protest 被提交時 |
| Protest 等待簽名 | 所有賽事工作人員 + 該選手 | 當工作人員代選手提交時 |
| Protest 裁決 | 所有賽事工作人員 + 該選手 | 當 jury accept / reject / withdraw 時 |

一旦選手報到（或被標記為 DNS / Late），提醒就會停止。

### 誰會收到通知

僅同時滿足以下所有條件的使用者：

- 已連結的選手帳號（上面的 Path A 或 Path B）
- 在作業系統層級啟用了通知
- 在應用程式中啟用了通知（預設：開）
- 一個有效的推播 token（在應用程式至少啟動一次時建立）

### 關閉通知

- iPhone：設定 → Apnea Comp → 通知 → 關閉。
- Android：設定 → 應用程式 → Apnea Comp → 通知 → 關閉。
- 在應用程式中：More → About → 通知開關。

關閉會立即從伺服器清除你的推播 token。

---

## 離線運作

應用程式被設計為在比賽進行中網路中斷時仍能繼續運作，這在泳池 / depth 場地很常見。

### 失去連線時會發生什麼

頂部會出現一個紅色列 **「You are offline」**。你仍然可以：

- ✅ 儲存 Judge 結果（本機儲存，稍後同步）
- ✅ 為選手 Check-in（本機儲存，稍後同步）
- ❌ 從 AIDA 載入新的選手名單
- ❌ 接收推播通知（重新連線時投遞，FCM 會保留它們）

### Offline 徽章

> ![選手卡片上的 Offline 徽章](../images/offline-badge.png)

當你在離線時儲存結果，選手卡片會顯示一個小的 **⛔ Offline** 徽章，而不是 AIDA 同步徽章。這表示：

- 結果在你裝置的記憶體中是 **安全** 的。
- 它 **尚未** 到達伺服器。
- 應用程式會在背景每 5 秒自動重試一次。

當網路恢復時，徽章會自動變為 **✅ AIDA**。無需手動操作。

### 手動同步

如果由於某種原因自動重試沒有跟上，請開啟 **Results**：

> ![Results 同步橫幅](../images/results-banner.png)

如果有任何待處理項，你會看到一個橙色橫幅：

- **「N offline result(s) waiting to sync」** 以及一個 **Sync now** 按鈕 — 點按立即重試。
- **「M results not synced to AIDA」** 以及一個 **Resync** 按鈕 — 用於 AIDA 一側的失敗（token、伺服器錯誤等）。

### ⚠️ 重要

離線結果會一直存在於你的裝置記憶體中，直到它們同步。**在有離線項待處理時，請勿強制關閉應用程式或重新開機手機** — 它們會遺失。請等待 ⛔ 徽章全部消失，或在退出前點按 Sync now。

如果你不確定，請開啟 Results 並尋找橙色橫幅。沒有橫幅 = 沒有待處理項。

---

## AIDA 整合

### 取得你的 token

在 <https://www.aidainternational.org> 登入你的 AIDA International 管理員帳號。開啟你註冊的比賽。尋找 API / Integration 部分以複製：

- **AIDA Token** — 看起來像一長串字母與數字。
- **AIDA Event ID** — 一個數字，通常為 4–6 位。

如果你看不到這些選項，則需要註冊該賽事的 AIDA 管理員來分享它們，或者需要更新你的帳號權限。

### 在應用程式中設定

Edit Event → 貼上兩個值 → Test Connection → Save。應用程式會將 token 安全地快取在伺服器上（絕不會在 URL 中暴露）。當你更新 token 時，新值會立即用於下一次儲存（無需重新啟動應用程式）。

### 同步什麼以及何時同步

- **讀取** — Setup → Load Athletes 拉取開始名單，包括姓名、AP、PB 與 discipline。
- **寫入** — Judge 中的每次 Save 都會傳送結果（RP、card、reasons、remarks、start offset）。在背景進行，不會阻塞。

### 同步失敗時

- **Token 過期 / 無效** → 紅色 SnackBar：*「AIDA token invalid — update in Edit Event」*（Organizer / Main Judge）或 *「ask Organizer to update」*（其他角色）。更新 token，然後 Results → Resync。
- **網路錯誤** → 卡片上的 🔁 Retry 徽章。點按它查看錯誤訊息並重試，或使用 Results → Resync 一次性完成。
- **離線** → ⛔ Offline 徽章。連線時自動重試；參見 [離線運作](#離線運作)。

### Mock mode

將 token 設為 `test` 或 `demo`（或將兩個欄位都留空）即可在沒有 AIDA 的情況下運作。應用程式會產生範例選手；不會傳送任何內容。用於訓練、演練或應用程式示範。Mock 模式的賽事會忽略真實世界的日期，因此倒數計時與語音提示會立即運作以便測試。

---

## 多日賽事

對於跨越多日的比賽：

- Setup → **Total Days** → 設為比賽天數。
- 每一天都有自己的開始名單、check-in、結果與 OT。
- 當有不止一天時，AppBar 下方會出現一個 **Day selector**。點按以切換。
- **Rest days**：在 Setup 中標記它們；它們在排程中會被略過。

資料 **不會** 在不同日之間結轉 — 在 Day 2 移動選手不會影響 Day 1。跨日的總分在 Results 中計算。

如果你的賽事在 AIDA 上註冊為多日，Load Athletes 會自動拉取每日的開始名單。

---

## 結果與匯出

**Results** 分頁顯示即時排名，隨著判定的錄入而更新。

- 頂部的 **摘要卡片**：選手總數、white / yellow / red、AP / PB / RP。
- **discipline 篩選** 以依項目縮小範圍。
- 頂部的 **同步橫幅**（如有）：Offline 待處理、AIDA 待處理或 token 問題。
- 依積分排序的 **選手清單**，點按查看詳情。
- **Export** — 分享一份 CSV，用於張貼在公告欄或傳送給選手。

### Rewards & 排名

**Rewards** 分頁（在 Athlete Mode 中也是一個分頁）依積分對選手排名，並依 discipline 與 gender 分組。

- **Day 標籤** — Total、Day 1、Day 2 … 以界定排名範圍。
- **Include yellow card scores** 開關。
- **Tiebreak**（右上 ⚙） — 拖曳以重新排列 tiebreak 規則。AIDA 預設（Rulebook §4.2.16）為：total points → **AP−RP 差最小** → Red 更少 → Yellow 更少 → White 更多。完全相同者共享同一名次，下一名次跳過（**奧林匹克並列**，例：兩個第 1 → 下一個是第 3）。深度 RP 以整數米輸入（§4.1.22.1）。
- Opener 與 invalidated（已 re-swim）的項目會被排除在排名之外；所有人仍會出現在 Results 中。
- **Export CSV** — ↓ 圖示分享一份 UTF-8 CSV（在所有語言中都能在 Excel / Numbers 中正確開啟），反映目前的 Day / Yellow / Tiebreak 設定。

---

### Records (WR/CR/NR) — 紀錄

標記並確認世界 / 大洲 / 國家紀錄挑戰。

1. **標記比賽** — 在建立或編輯比賽時，在 **Record Attempts** 中開啟 **World Record** / **Continental**。之後比賽卡片和 Results 頂部會顯示 🏅 徽章。
2. **檢查紀錄** — 在 **Results** 標籤點按 **Check WR/CR/NR**。對每位白卡選手，App 會依國籍、項目、性別查詢 AIDA 官方紀錄並建議 WR / CR / NR。需要連網 — 無法取得的會跳過。
3. **確認** *(Organizer / Main Judge)* — 建議顯示為虛線徽章（如「WR?」）。點按以確認等級或清除。已確認的紀錄顯示為實線徽章，並包含在 CSV 匯出中。

> 僅白卡（有效）成績可作為紀錄。帶罰分的成績不能成為世界或大洲紀錄（Rulebook §10.2）。建議是將實現成績（RP）與當前紀錄比較，最終由裁判決定。


## 顯示 & 語言

這兩項設定都在頭像選單（右上角）中，並會即時套用於整個應用程式。

### Theme

> ![Theme 選擇器](../images/theme-picker.png)

點按你的頭像 → **Theme** → 選擇 **System default**、**Light** 或 **Dark**。

### Language

> ![Language 選擇器](../images/language-picker.png)

點按你的頭像 → **Language** → 選擇 **System default**、**English**、**한국어**、**日本語**、**简体中文** 或 **繁體中文**。應用程式會立即切換並記住你的選擇。

比賽標準術語在每種語言中都保持英文 — OT、AP、RP、PB、discipline 代碼（STA、DYN、…）、WHITE / YELLOW / RED、角色名稱與 Line — 這樣來自不同國家的工作人員讀到的是相同的標籤。

---

## FAQ

### 工作人員的手機沒電了 — 我會遺失他們的錄入嗎？

不會。他們儲存結果後，結果會立即儲存到伺服器（如果離線則儲存在他們的裝置上）。同一賽事中的其他裝置會立即看到該結果。即使他們的手機永久遺失，唯一有風險的也只是未同步的離線結果 — 而且只有在故障那一刻有任何待處理項時才會如此。

### 兩個人正在查看同一位選手並儲存不同的結果

最後儲存的勝出。應用程式目前不會對並行編輯發出警告。請透過口頭協調來避免這種情況 — 通常只有一名裁判錄入某個特定結果。

### 某選手顯示 AP / PB 但沒有 startId — 為什麼？

很可能他們是在 Mock mode 中新增的，或是在 AIDA 之外手動匯入的。AIDA 同步需要 startId；這些選手的結果不會傳送到 AIDA（不顯示徽章）。他們仍會出現在 Results 中。

### 我變更了 AIDA token，但舊結果仍然失敗

開啟 Results → 如果橫幅顯示「Update token & resync」→ 點按它。待處理項會用新 token 重新傳送。應用程式將憑證快取在伺服器上，並在你儲存 Edit Event 時重新整理快取，因此無需重新啟動應用程式。

### 報到期間網路中斷會怎樣？

報到會儲存在本機，選手卡片會顯示一個小的 ⛔「Offline」徽章。連線一恢復，報到就會自動（在 5 秒內）同步到伺服器。選手無需再次簽名。簽名繪製本身不會被儲存 — 它僅在當下用於視覺確認。

### 某選手收不到推播通知

常見原因：

- 該選手已註冊但尚未連結到某條 AIDA 選手紀錄（未找到自動比對，也未兌換 invite code）。沒有這種連結，系統就不知道哪位選手是他們。
- 在作業系統層級通知被停用。iPhone：設定 → Apnea Comp → 通知。Android：設定 → 應用程式 → Apnea Comp → 通知。
- 應用程式尚未在新裝置上啟動過 — 推播 token 在啟動時簽發。
- 該選手已被標記為 DNS / Late / 已報到（在這種情況下，報到提醒會刻意停止）。

### 我可以刪除賽事嗎？

可以。Organizer 或 Main Judge 可以刪除賽事 — 在賽事清單中滑動它，或使用 **Edit Event → Delete**。刪除是永久性的，會移除該賽事的所有資料（選手、結果、紀錄、check-in 狀態、protests）。檔案儲存空間中已產生的 protest PDF 在整賽事刪除時不會被自動移除；如果你需要將它們清除，請聯絡我們。

### 某個 protest 卡在「Awaiting signature」上，而選手無法簽名

這發生在目前簽名流程之前建立的舊 protest 上。Organizer 或 Main Judge 可以開啟 **More → Protests → 該 protest → 🗑** 並刪除它。參見 [Protests → 刪除 protest](#protests申訴)。

### 應用程式顯示「Update required」畫面，且不讓我進入

你安裝的版本低於運營者為現場使用設定的最低版本。從 App Store / Play Store 更新到最新版本，然後重新開啟 — 應用程式會重新檢查並放你通過。

### 我需要在比賽當天一直開著應用程式嗎？

是的，在用於判定或報到的裝置上。應用程式不會在背景執行。如果你切換到另一個應用程式，螢幕狀態會被保留，但離線自動重試會暫停，直到你重新開啟應用程式。

**應用程式會在每一個畫面上防止螢幕自動鎖定**，因此你可以把裝置放在桌上而它不會熄滅。正因如此，電量會比平常消耗得更快 — 對於整天賽事，請讓裝置一直接著充電器。

推播通知本身不需要應用程式處於開啟狀態 — 只要你允許了通知，即使應用程式關閉，iOS / Android 也會投遞它們。

### 支援哪些裝置？

iPhone（iOS 15+）與 Android（Android 9+）。平板可以使用，但版面針對手機進行了最佳化。

---

## 疑難排解

### Judge 中出現「Could not save」紅色 SnackBar

這表示應用程式甚至無法在本機儲存結果 — 通常是因為選手已載入，但本機清單失去了同步。點按 **Reload**（Setup）並重試。為便於診斷，錯誤訊息中包含 athlete ID 與目前計數。

### 「AIDA token invalid」一直出現

- 在 Edit Event 中確認 token 沒有前導/尾隨空格。
- 點按 Test Connection — 它成功嗎？
- 如果 Test 失敗：聯絡你的 AIDA 管理員簽發一個新 token。
- 如果 Test 通過但儲存仍失敗：開啟 Results → Resync。

### 應用程式顯示「You are offline」但我明明在線上

連線性檢查會 ping 伺服器。如果伺服器短暫無法到達（罕見），或你的網路攔截了 Supabase URL（在飯店 / 公共 wifi 上不常見），指示器可能會保持紅色。無論如何都試著儲存一個結果 — 如果成功，指示器會在幾秒內消除。

### OT Delay 圖示不見了

檢查：

- 你是否在 **Start List** 或 **Judge** 分頁（圖示在其他分頁會隱藏）。
- 你的角色是否為 Organizer 或 Main Judge（其他角色看不到它）。
- 查看 AppBar 右側，角色徽章的正前方。

### Line Assignment 之後日程看起來不對

OT 計算在儲存時執行。如果你重新排序了選手但看到錯誤的 OT，向上捲動並再次點按 **Save** — 時間現在應當與順序相符。如果仍不符，請附上截圖聯絡我們。

### 某個團隊成員卡在 Pending 上

開啟 Users 分頁 → 找到他們的姓名 → 指派角色（Judge / Staff / …）。需要依每個賽事進行核准；核准不會在賽事之間結轉。

### 我已經判定了選手，但 Results 畫面是空白的

下拉重新整理。如果仍為空白，切換到另一個分頁再切回。如果問題持續，請截圖並聯絡我們 — 這不應該發生。

### 我換手機後推播通知不再運作

在新手機上登入並啟動一次應用程式。新裝置的推播 token 會取代你帳號中的舊 token。舊手機將不再收到通知。

---

## 隱私與資料

有關 App 收集哪些資料、如何處理以及你的權利的完整詳情，請參見 [隱私政策](https://elfreediving.github.io/aida-competition-privacy/zh_TW/PRIVACY_POLICY)。

簡要概述：

- **儲存什麼** — 你的帳號電子郵件、顯示名稱、個人頭像（如果你上傳了）、AIDA athlete UUID（如果你以選手身分註冊）、推播通知訂閱 ID（如果啟用了通知），以及你錄入的比賽資料（選手結果、check-in 狀態、活動紀錄與 protests）。
- **Protest 簽名** — 當提交 protest 時，選手（及 jury）手繪的簽名 **會** 作為正式 protest 紀錄的一部分被儲存，並嵌入到一份產生的 PDF 中。這是下面規則的唯一例外。
- **不儲存什麼** — 選手的聯絡方式、照片、出生日期、**check-in** 簽名繪製（check-in 板僅用於視覺確認），或 AIDA 公開揭露內容之外的任何個人識別符。
- **儲存在哪裡** — Supabase（目前為美國區域），靜態加密，僅透過依賽事劃分資料範圍的 Row-Level Security 政策存取。推播通知經由 OneSignal 傳輸，OneSignal 再將其轉發到 APNs（iOS）與 FCM（Android）。
- **AIDA tokens** — 加密，僅 Organizer / Main Judge 角色可存取，絕不會在 URL 中暴露，也不會在用戶端記憶體中停留超過必要時間。
- **離線緩衝** — 離線時儲存的 judge 結果僅存在於 App 的記憶體中，並在重新連線後數秒內同步。
- **本機裝置儲存** — **Remember email** 會將你的電子郵件儲存到標準本機儲存空間（SharedPreferences / NSUserDefaults）。如果你啟用 **Remember password**，它會將你的密碼儲存到裝置的安全金鑰庫（iOS Keychain / Android EncryptedSharedPreferences），絕不會儲存到我們的伺服器。你的主題與語言選擇也會儲存在本機。登出或解除安裝即可清除已儲存的憑證。

---

## 聯絡方式

如有 bug、問題或意見回饋：

- Email: lee33179@gmail.com

回報問題時，請包含：

- 裝置型號與作業系統版本
- 應用程式版本（More → About）
- 如相關，請附截圖
- 問題發生的大致時間（以便我們與紀錄比對）

---

最後更新: 2026-06-02。
