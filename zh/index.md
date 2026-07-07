# Apnea Comp — 用户手册

**AIDA Competition Management System**

本手册涵盖使用 Apnea Comp 运营一场自由潜水比赛的全过程，从设置到结果。应用内的 Help（More → Help）是快速参考；本文档更为深入，包含运营场景和故障排查。

如果你只有五分钟，请阅读下面的 **快速开始** 以及底部的 FAQ。

---

## 目录

1. [开始之前](#开始之前)
2. [快速开始](#快速开始)
3. [角色及其权限](#角色及其权限)
4. [创建赛事（Organizer）](#创建赛事organizer)
5. [加入赛事（Staff）](#加入赛事staff)
6. [作为选手加入](#作为选手加入)
7. [Setup：选手、Line 和 OT](#setup选手line-和-ot)
8. [Break Times](#break-times)
9. [团队赛（Team）](#团队赛team)
10. [Check-in](#check-in)
11. [Start List & Speaker Mode](#start-list--speaker-mode)
12. [输入判定结果](#输入判定结果)
13. [罚分（Rulebook 17.8）](#罚分rulebook-178)
14. [Protests（申诉）](#protests申诉)
15. [Re-swim & Opener](#re-swim--opener)
16. [日程调整（OT Delay）](#日程调整ot-delay)
17. [推送通知](#推送通知)
18. [离线运行](#离线运行)
19. [AIDA 集成](#aida-集成)
20. [多日赛事](#多日赛事)
21. [结果与导出](#结果与导出)
22. [显示 & 语言](#显示--语言)
23. [FAQ](#faq)
24. [故障排查](#故障排查)
25. [隐私与数据](#隐私与数据)
26. [联系方式](#联系方式)

---

## 开始之前

你将需要：

- 一部安装了 Apnea Comp 应用的 iPhone 或 Android 设备。
- 稳定的网络连接（比赛当天为可选 — 参见 [离线运行](#离线运行)）。
- 如果赛事将进行正式计分，需要 AIDA International 账户（仅 Organizer）。
- 对于 Organizer：该比赛的 AIDA Token 和 Event ID。没有它们，应用将以 🧪 Mock mode 运行（示例数据，无 AIDA 同步）。

我们建议每位裁判 / 工作人员使用自己的设备。应用支持多人同时在同一赛事中工作 — 结果会在设备之间实时同步。

---

## 快速开始

### 面向 Organizer（赛事创建者）

1. 打开应用，在 Events 界面点按 **+**。
2. 输入赛事名称、类型（Pool / Depth / Team）、日期，然后点按 Create。
3. 打开赛事 → **Edit Event** → 粘贴 **AIDA Token** 和 **AIDA Event ID** → 点按 **Test Connection** → Save。
4. Setup 标签页 → **Load Athletes** 从 AIDA 拉取开始名单。
5. Setup 标签页 → 设置 **Lines**（泳道数量）、**First OT** 和选手之间的 **Interval**。
6. 将（在 Edit Event 中可见的）赛事 **invite code** 分享给你的工作人员。
7. 工作人员加入时在 **Users** 标签页中批准他们（他们会显示为 Pending）。

### 面向 Staff（裁判、签到人员等）

1. 打开应用，登录。  
   *提示：勾选 **Remember email** 可在下次预填你的邮箱。你也可以勾选 **Remember password** — 此时密码会保存在设备的安全密钥库中（iOS Keychain / Android EncryptedSharedPreferences），绝不会保存在我们的服务器上。登出会同时清除两者。*
2. Events 界面 → 点按 **Join with code** → 粘贴 invite code。
3. 在 Organizer 批准你并分配角色（Judge、Main Judge、Staff 等）之前，你会显示为 Pending。

### 面向选手

1. 打开应用，用你的邮箱注册。
2. 注册时选择 **I am an athlete**。
3. 应用会尝试自动将你的姓名与 AIDA 的开始名单匹配。
4. 如果匹配成功，你注册的赛事会立即出现。如果你的姓名有重名，请向 Organizer 索取一次性 invite code。

现在你已准备好运营当天的比赛。

---

## 角色及其权限

| 角色 | Setup | Judge | Check-in | Users | Log | OT Delay | Send Push |
|------|-------|-------|----------|-------|-----|----------|-----------|
| 👑 Organizer | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ⚖️ Main Judge | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ✏️ Judge | — | ✅ | ✅ | — | — | — | — |
| 👀 Staff | — | 查看 | ✅ | — | — | — | — |
| 🏊 Athlete | — | — | — | — | — | — | — |
| ⏳ Pending | — | — | — | — | — | — | — |

- **Organizer** 是创建赛事者的默认角色。
- **Main Judge** 拥有与 Organizer 相同的权限；在 Users 中分配。
- **Athlete** 为只读 — 仅开始名单和个人结果。无法访问其他成员的数据、AIDA token 或控制功能。
- **Pending** 成员需等待 Organizer 或 Main Judge 在 Users 中批准并分配真正的角色。

---

## 创建赛事（Organizer）

### 基本信息

- **Name** — 对你的工作人员可见。
- **Type** — 🏊 Pool、🌊 Depth 或 👥 Team。
- **Dates** — 对于多日赛事，选择开始和结束日期。

### AIDA 集成（推荐）

打开赛事 → **Edit Event** → 填写：

- **AIDA Token** — 来自你的 AIDA 管理面板。
- **AIDA Event ID** — AIDA 比赛的数字 ID。

点按 **Test Connection**。绿色对勾表示凭据有效，应用可以读取开始名单。Save。

> ![带有 AIDA 字段的 Edit Event 界面](../images/edit-event-aida.png)

如果你将这些留空，或将 token 设为 `test` 或 `demo`，应用将以 🧪 **Mock mode** 运行 — 它会生成用于练习的示例选手。Mock mode 不会向 AIDA 发送任何内容。

### 邀请你的工作人员

invite code 显示在 **Edit Event** 中。通过你常用的渠道（聊天、邮件、纸张）分享它。工作人员在 Events 界面使用 **Join with code** 输入该代码。

> 提示：尚不支持轮换 invite code。请像对待密码一样对待它，只与应该加入团队的人分享。

---

## 加入赛事（Staff）

1. 登录应用。
2. 在 Events 界面，点按 **Join with code**。
3. 粘贴代码。赛事会以 **Pending** 状态出现在你的列表中。
4. 等待 Organizer 批准你并分配角色。批准后你会看到赛事变为可点按。

如果你不小心用错了代码，请让 Organizer 在 Users 中移除你，以便重新尝试。

---

## 作为选手加入

如果你是参赛而不是运营赛事，请以选手身份注册，以查看你的开始名单、OT、line 和个人结果。

你可以随时在工作人员视图和选手视图之间切换：点按你的头像（右上角）→ **Switch to Athlete Mode**（返回时用同样的方法）。

### 工作原理

当你注册时，应用会读取你的姓名，并尝试将其与 organizer 已从 AIDA 加载到应用中的选手进行匹配。如果恰好找到一个匹配项，你的账户会自动关联。否则，organizer 可以签发一次性 invite code。

### Path A — 自动匹配（大多数情况）

1. 用你的邮箱注册。
2. 选择 **I am an athlete**。
3. 完全按照在 AIDA 注册的内容输入你的 **first name**、**last name**、**gender** 和 **nationality**。
4. 应用搜索已加载的赛事。如果你的姓名与单个选手匹配，且 gender / nationality 一致，你会立即被关联。
5. Events 界面现在会显示你所出现的赛事。点按其中一个即可查看你的开始名单以及（之后的）结果。

### Path B — invite code（当姓名冲突时）

如果两名选手同名，自动匹配无法判断哪一个是你。请向 Organizer 索取 invite code：

1. Organizer 打开赛事 → **Athlete Invite Codes** → 在列表中找到你的姓名 → 点按它生成一个 6 字符代码。
2. Organizer 私下将代码发送给你。
3. 你打开应用 → Events → **Enter invite code** → 粘贴它。
4. 应用验证代码并关联你的账户。

### broadcast（激活）code — 加入的最快方式

Organizer 可以开启一个 **broadcast code**（在界面上显示为 **Athlete code**），任何选手都能用它直接加入赛事 — 当还没有 AIDA start list 时，或对于不在名单上的选手，这非常有用。

**Organizer：** 打开赛事 → **Setup** → 点按 *Athlete code* 旁边的绿色 **+** 来生成它，然后 **复制** 并分享（聊天、纸张、投影）。随时点按电源图标即可将其关闭。

**Athlete：** 打开应用 → Events → **Enter code** → 粘贴 broadcast code。加入后你即可查看 start list 和结果，并提交你的文档。

> ![Setup — Athlete (broadcast) code](../images/broadcast-code.png)

### Find me on AIDA

> ![Find me on AIDA 搜索](../images/aida-find-me.png)

如果自动匹配没有找到你，你可以手动关联你的 AIDA 选手资料。在 **Edit Profile** 或 **Athlete Setup** 中，点按 **Find me on AIDA**，输入你的姓名，并从结果中选择你的资料。这会保存你的 AIDA athlete ID，使你的结果正确匹配。🔄 sync 图标还会拉取你注册的赛事。（没有比赛历史的选手可能不会出现在搜索中 — 这种情况下，请完全按照在 AIDA 注册的内容手动输入你的姓名、nationality 和 gender。）

### 你能看到什么

Athlete Mode 有四个标签页：**My Info**、**Start List**、**Results** 和 **Rewards**（过往赛事显示三个 — 无 Start List）。

- 🏊 Athlete 角色：对你所出现的赛事的只读访问。
- **My Info** — 你被分配的 OT、line、check-in 状态（Pending / Checked-in / DNS / Late）以及你的结果。你也可以在这里提交申诉（参见 [Protests](#protests申诉)）。
- **Start List** — 当天的进行顺序，带有「Show my line only」筛选。
- **Results** — 已发布的结果。
- **Rewards** — 按 discipline 和 gender 排列的积分排名，你的行会被高亮。

你无法看到其他选手的个人信息、裁判的笔记或 AIDA token。

### 推送通知

如果你允许通知，你会收到：

- **Start list published** — 当 Organizer 发布当天的开始名单时。
- **Unofficial / Official results** — 当结果发布时。
- **OT delay** — 如果日程变动且你的 OT 改变时。
- **Check-in 截止提醒** — 自动发送，仅当你尚未签到时：
  - check-in 截止（即 OT − 1h）前 1 小时
  - check-in 截止前 30 分钟
- **Protest 更新** — 如果有关于你的 protest 被代为提交（要求你签名），或被 jury 裁决时。

通知文本会以你选择的应用语言到达。你可以随时在设备的系统设置或应用的 About 界面中关闭通知。

---

## Documents (同意书)

许多赛事要求选手在参赛前提交 AIDA 同意书。打开 **My Info → Documents**。

- **必需表单** — Competition Entry、Image Rights 同意书和 Liability 免责声明。**Medical Statement** 为可选项，但通常会被要求。
- **两种提交方式** — *在应用内填写*（输入各字段并在屏幕上签名，系统会为你生成 PDF），或*上传*已签名的纸质副本*照片*。
- **Medical Statement** — 自签发之日起一年内有效。将其保存到个人资料中（Edit Profile → Medical Statement），即可在多个赛事中重复使用。如果上传照片，请输入证书上显示的签发日期。签发日期*之后*发生的压力性损伤或晕厥会使证书失效——请重新提交一份。
- **截止时间** — 如果到赛事前一天仍缺少必需表单，你会收到一条列出缺失项的推送提醒。

**面向工作人员 (Organizer / Main Judge):** 打开 **More → Documents**，可查看每位选手的提交状态、打开文件，并**将全部内容下载为 ZIP**（按文档类型分文件夹）。当选手申报受伤或晕厥时，该 medical statement 会被标记为**人工核验**——当面确认证书后，点按 *Mark verified*。已提交的文档在赛事结束后保留 15 天，之后删除。

---

![Athlete — My Info → Documents](../images/documents-athlete-list.png)

![Fill in app and sign](../images/documents-fill-sign.png)

![Medical Statement saved on profile](../images/documents-medical-profile.png)

![Staff — Documents status & manual-check](../images/documents-staff-status.png)

![Staff — verify medical statement](../images/documents-staff-verify.png)

## Setup：选手、Line 和 OT

> ![Setup 界面布局](../images/setup-screen.png)

Setup 是你决定当天日程的地方：每位选手在哪条 line 游泳、他们的 OT（official time）是什么时候，以及当天有哪些休息。

**自动保存** — 你在 Setup 中所做的每项更改都会自动保存到服务器。如果你离开应用再回来，你的设置会被恢复。如果共同 organizer 从 AIDA 重新加载选手，日程仍会遵循你的 line 配置。

### 加载选手

- **Load Athletes** — 从 AIDA 拉取已注册的开始名单。幂等：重新加载时现有的判定会被保留。
- **Mock mode** — 生成用于练习的示例开始名单。

### 配置 Line 和 OT（基本）

- **Lines** — 泳道数量（Pool）或平台 line 数量（Depth）。
- **First OT** — 第一位选手开始的时间（例如 `09:00`）。
- **Interval** — 同一条 line 上相邻选手之间的间隔。
- **Depth Line Interval**（仅 Depth / Team） — 当 **ON** 时，各 line 依次进行：每条 line 以错开的偏移量开始（Line 1，然后几分钟后 Line 2 …），且 Start List 会显示每条 line 的倒计时。该偏移量必须满足 `(lines − 1) × line_interval < athlete_interval`，否则无法生成日程。当 **OFF** 时，所有 line **并行** 进行 — 同一行的选手共享相同的 OT，与 Pool 模式完全一样。

### Advanced Setup（可选，可折叠）

> ![Advanced Setup 折叠](../images/setup-advanced-collapsed.png)
> ![Advanced Setup 展开](../images/setup-advanced-expanded.png)

点按 **Advanced Setup** 可展开更多选项以进行精细控制：

- **按 discipline 设置 line（仅 Pool）** — 为每个 discipline 分配不同数量的泳道。例如，STA 使用 4 条泳道，但 DYN/DNF 仅使用 2 条泳道。应用会为每个 discipline 生成独立的子日程，并将它们拼接在一起。
- **跨 discipline 的泳道延续** — 当上一个 discipline 在 line 中途结束（例如 STA 在 4 条泳道中的第 3 条结束）时，下一个 discipline 既可以从泳道 1 重新开始（默认），也可以从泳道 4 继续。当裁判在不同 discipline 之间留在同一条泳道时很有用。

- **Custom Intervals（单独设置间隔）** — 在基本间隔之外，按出发顺序号区间设置不同间隔。例如：#1–#10 → 10 分钟，#11–#20 → 8 分钟，#21–#30 → 7 分钟。点按 **Add interval（添加间隔）** → 设置 *起始顺序 / 结束顺序 / 间隔* → **Done**。OT 会自动重新计算并保存。此为按日设置；区间不可重叠且需在选手数以内；没有区间则全部应用基本间隔。若当天存在手动休息，则跳过 OT 重算（与 Save Configuration 相同 — 保护手动调整的 OT）。

### Line 分配

加载选手后，打开 **Assign Lines** 在 line 之间移动并重新排序。OT 会自动重新计算：

- Pool：轮流分配，OT 取决于在 line 内的位置。
- Depth：含 line 循环的完整序列，并考虑 depth line interval 规则。

**直接 line 分配** — 对于特殊情况（例如为国家纪录尝试保留某条特定 line，或放置 re-swim — 参见 [Re-swim & Opener](#re-swim--opener)），点按一位选手，然后点按目标 line 和位置。日程会重新排布以遵循你的选择。

完成后 Save — 当天的开始时间至此确定。

---

## Break Times

休息会让日程暂停一个固定的时间段。应用支持两种休息。

### Time-based 休息（Lunch Break 等）

> ![Setup 中的 Time-based 休息](../images/break-time-based.png)

用于所有人事先约定好的固定时间休息（午餐、颁奖典礼等）：

1. 打开 Setup → **BREAK TIMES** → **Add Break Time**。
2. 选择 **Time-based**。
3. 输入开始时间和结束时间（例如 `12:00` – `13:00`）。
4. 保存。

任何 OT 落在休息时间段内的选手都会被向后推，使其 OT 落在休息结束之后。泳道分配会被保留。

### After Athlete 休息（Build 48 新增）

> ![正在添加的 After Athlete 休息](../images/break-after-athlete-add.png)
> ![已列出的 After Athlete 休息](../images/break-after-athlete-listed.png)

当你需要在 **某位特定选手完成之后** 插入休息时使用，与钟表时间无关。典型场景：热身选手结束后，你希望在正式选手开始前有 60 分钟的休息。

1. 打开 Setup → **BREAK TIMES** → **Add Break Time**。
2. 选择 **After Athlete**。
3. 选择标志该段结束的选手。
4. 输入休息时长（例如 `60` 分钟）。
5. 保存。

被选中的选手以及 **开始名单顺序中其后的每一位选手** 都会被推迟该休息时长。其他 discipline（顺序在前、即便钟表时间相同的选手）不受影响。泳道分配会被保留。

要移除某个休息，点按 BREAK TIMES 列表中它旁边的 🗑️ 垃圾桶图标。

---

## 团队赛（Team）

Team 类型的赛事（赛事类型 **Team**）将选手分入各队伍，由队伍的合计分数决定名次。**Setup** 中会出现一个 **Teams** 区块 — 仅针对 Team 类型的赛事。

> ![Setup 中的 Teams 区块](../images/team-setup.png)

### 创建与编辑队伍

点按 **New Team** 打开队伍编辑器。

> ![队伍编辑器 — 名称、颜色、成员](../images/team-edit.png)

- **名称** — 必填。
- **颜色** — 选一个颜色，便于在列表中辨认队伍。
- **成员** — 勾选属于该队伍的选手。列表可按姓名或 nationality 搜索。选择一位已在其他队伍中的选手，会将其移动过来。

每张队伍卡片都会显示其名称、颜色和成员数。点按卡片可 **编辑**，或使用其菜单 **删除** 它。

> 在多日出场的选手只会显示一次 — 选择该选手会将其 **所有日的条目** 都分配给该队伍，因此每个人只需挑选一次。

---

## Check-in

选手在热身前签到。打开 **Check-in** 标签页。

- 点按一张处于 pending 状态的选手卡片，打开签名表。
- 选手在屏幕上签名，点按 **Save** → 该选手以当前时间被标记为 Checked In。卡片随后会同时显示 OT 和签到时间。
- 对于缺席者：点按选手 → 确认 **DNS**（Did Not Show）。
- 对于超过截止时间的迟到者：点按 → **Late Check-in**。他们会自动获得带「Late Check-in」remark 的 Red 卡。
- **自动 Late Check-in** — 在 check-in 截止（OT − 1h）过后仍处于 pending 的选手会被自动标记为 **Late Check-in**。pending 列表会以 `Check-in HH:mm` 显示每位选手的截止时间。
- **AIDA 同步** — DNS 和 Late Check-in 会像判定结果一样自动提交到 AIDA（作为 Red 卡 / 0 分）。你不再需要在 Judge 中手动输入这些。
- 点按顶部的迷你卡片（In / Late / DNS / Pending）可将列表筛选为该组。

> 签名绘制仅用于视觉确认 — 它在签到那一刻向工作人员显示，并在表单关闭后立即被丢弃。我们不会在任何地方存储签名图像（既不在服务器上，也不在设备上）。仅记录已采集签名这一事实，以及签到时间。

> Check-in 也可离线工作。如果你在确认时设备处于离线状态，签到会被保留在设备内存中，卡片上带有一个小的 ⛔「Offline」徽章，并在重新连接后 5 秒内自动同步到服务器。参见 [离线运行](#离线运行)。

---

## Start List & Speaker Mode

> ![带倒计时的 Start List 界面](../images/start-list-countdown.png)

Start List 标签页显示当天的进行顺序，以及距下一位选手 OT 的实时倒计时。每个 OT 临近时，应用会朗读倒计时，使选手和裁判无需盯着屏幕即可听到。

### 语音倒计时

每个 OT 临近时，应用会播放语音提示，使选手和裁判无需盯着屏幕即可听到读数。这些提示是 **预先录制的音频文件**，因此在 **iOS 和 Android 上听起来完全相同**（早期版本使用每部手机内置的 text-to-speech，各设备之间有所不同）。

OT 之前的提示：
`2:00`（「two minutes to official top」）、`1:30`、`1:00`、`0:30`、`0:20`、`0:10`，然后 `5 — 4 — 3 — 2 — 1`，并在 OT 时：**「official top」**。

出发窗口期间（OT 之后）的提示：在 +1 秒时 **「plus one」**，随后随着窗口走完会报出经过的秒数 — 直到该 discipline 的上限 — 如果选手在窗口结束前仍未出发，则以 **「start cancelled」** 结束。

### 语音播报（Announce）

Start List 上有一个 **Announce（语音播报）** 按钮。点按它，输入「距 OT 还有几分钟」的分钟数，设备的 text-to-speech 便会朗读 **「N minutes to Official Top」**（使用设备语言）。

这是一次手动的单次播报，与自动倒计时提示（语音倒计时）相互独立。它会按设备语言（en / ko / ja / zh / zh_TW）发声。

### 静音按钮

> ![Start List 上的静音切换](../images/start-list-mute.png)

点按 AppBar 中的 🔊 / 🔇 图标可切换语音播报。在以下情况很有用：

- 你在一个已有独立 PA 系统播报的室内泳池中运营。
- 选手更喜欢无声倒计时。
- 你临时进入会议，需要让设备安静下来。

静音只对你切换它的那台设备生效 — 同一赛事中的其他设备会继续播报。无论如何，视觉倒计时都会继续运行。

### Speaker Mode

> ![Speaker Mode 已激活](../images/speaker-mode.png)

Speaker Mode 将设备变成一个 **专用倒计时播报器** — 非常适合场馆的主扬声器。一旦启用：

- 屏幕被锁定在 Start List 视图；其他标签页被隐藏。
- 静音被强制关闭（不会被意外静音）。
- 屏幕保持常亮（无自动锁定）。
- 退出 Speaker Mode 需要 PIN，因此好奇的旁观者不会意外关闭它。

**后台播放** — 在 Speaker Mode 下，语音（倒计时提示 + 语音播报）即使在你将应用切到后台或锁屏后仍会继续播放。iOS 通过保持一条静音的 keep-alive 音轨来实现；Android 使用一条前台服务通知（**「Start list countdown active」**）。这样即便手机锁屏，场馆的扬声器也会持续播报。此行为仅限 Speaker Mode。

**要启用**：打开角色 / 个人资料菜单 → **Speaker Mode** → 设置一个 4 位 PIN。

**要退出**：点按 Speaker Mode 徽章 → 输入 PIN → 确认。

推荐设置：将一部专用手机或平板插入场馆的音响系统，并在整个比赛日保持 Speaker Mode。让它一直接着充电器 — 语音播放比被动空闲更快耗电。

### 屏幕常亮

应用会在 **每一个** 界面上保持屏幕常亮，而不仅仅是 Start List，因此即使你不触碰设备，倒计时和通知也能工作。这是一个全局设置 — 你一打开应用它就生效。注意：对于全天赛事，请让设备一直接着充电器；电量会比平常消耗得更快。

---

## 输入判定结果

> ![带有选手卡片的 Judge 标签页](../images/judge-tab.png)

Judge 标签页显示当天的所有选手。点按一张卡片以输入结果。

### 输入结果

1. **RP** — 实际表现（static 为时间，dynamic 为距离，depth 为深度）。
2. **卡片** — White（干净）、Yellow（罚分）或 Red（DQ）。
3. **罚分原因** — 选择 White 以外的卡片时必填。参见 [罚分](#罚分rulebook-178)。
4. **Start offset** — 提前（负数）或延迟（正数）的秒数。用于出发窗口罚分的计算。
5. **REMARKS** — 对于某些原因（BO、Other Penalty、DQ Other 等）必填。应用会预填一个模板；请补全缺失的细节。
6. 点按 **Save Result**。

### 卡片徽章

保存后，你会在选手卡片上看到一个小徽章：

- **✅ AIDA** — 已同步到 AIDA International。
- **🔁 Retry** — 同步到 AIDA 失败；点按可查看原因并重试。
- **⛔ Offline** — 已在此设备上本地保存；恢复在线后将自动同步。参见 [离线运行](#离线运行)。

如果未显示徽章，则表示未配置 AIDA 集成（该选手没有 startId）— 在 Mock mode 中这是正常的。

---

## Judge Calculator（判定计算器）

为减少现场算术，应用为 Pool 项目内置了 RP 计算器。打开一张选手卡片，在选手详情表中即可找到对应工具。计算结果可通过 **Fill RP** 一键写入 RP 字段。

### Pool Length（泳池长度）

在赛事 **Setup** 中设置 **Pool Length（m）**。该设置仅出现在 **Pool 和 Team** 类型的赛事中（Depth 不适用）。使用 Distance Calc 时必须先填写它。

### Distance Calc（DYN / DYNB / DNF）

在 **Judge** 标签页 → 选手详情表 → 点按 📏 尺子（ruler）按钮。输入完成的 lap 数量以及最后一段的零头 m 数。结果 = lap × Pool Length + 零头距离。点按 **Fill RP** 将其写入 RP。

### STA Average Calc（STA）

在选手详情表中点按 ⏱ 计时器按钮。输入两位裁判各自测得的时间（mm:ss）。应用取两者平均（四舍五入到最接近的秒），然后点按 **Fill RP** 写入。

> 如果计算出的 **RP 小于 AP**，White 卡会被自动禁用 — Under AP 的表现不能给 White。
>
> Depth 项目（CWT、CWTB、FIM、CNF）没有计算器 — 请手动输入 RP。

---

## 罚分（Rulebook 17.8）

应用遵循 AIDA Rulebook 第 17.8 节。原因按卡片颜色分组。

### 🟨 Yellow 卡原因

- **Start** — 不正确的出发技术（Pool DYN：墙壁出发失败等）。
- **Early Start** — 在 OT 之前出发。在出发窗口内，每提前 5 秒罚 1 分。
- **Late Start** — 在 OT 之后出发。在出发窗口内，每延迟 5 秒罚 1 分。
- **Grab** — 在表现过程中拉拽了 line、墙壁或平台。
- **Other Penalty** — 未涵盖的其他任何情况。**REMARKS 必填**。

### 🟥 Red 卡原因

- **Surface Protocol** — 出水 15 秒内的 surface protocol 不正确。
- **Blackout Surface** — 在水面失去运动控制或意识。**REMARKS 必填**（恢复时间等）。
- **Blackout UW** — 水下黑视。**REMARKS 必填**。
- **DQ Late Start** — Late Start 超过出发窗口（Pool +10s、Depth +30s）。
- **Jump Start** *(仅 Pool DYN)* — 在 OT 之前离开墙壁。
- **DQ Other** — 因任何其他原因取消资格。**REMARKS 必填**。

### 出发窗口

| Discipline | 窗口 | 窗口内 | 超过窗口 |
|------------|--------|----------------|-------------|
| Pool | ±10 s | 每 5 秒 1 分（Yellow Early/Late Start） | 延迟一侧为 DQ Late Start（Red）；提前的 Pool 墙壁出发为 Jump Start（Red，仅 DYN） |
| Depth | ±30 s | 每 5 秒 1 分（Yellow Early/Late Start） | 延迟一侧为 DQ Late Start（Red） |

### REMARKS

AIDA Rulebook 4.1.16.2 要求为每个 Yellow 和 Red 提供书面原因。如果某原因要求填写 REMARKS 而它为空，Save 按钮会阻止该操作。

当你选择一个原因时，REMARKS 字段会预填一个模板（例如 `BO Surface, recovery: ___`）。保存前请补全缺失的细节 — 这是正式记录。

### 多选与组合卡

> ![Red 卡多选表](../images/judge-red-multi-select.png)

当你点按 Red 卡时，原因表会以两个分组同时显示 **Red 和 Yellow** 两类原因：

- **DQ Reason (Red)** — Surface Protocol、Blackout Surface、Blackout UW、Airways、DQ Late Start、Jump Start、Pull、Touch、Other Lane、Check-in DQ、DQ Other
- **Additional Penalty (Yellow)** — Under AP、No Tag、Grab、Pull、Turn、Start、Early Start、Late Start、Lanyard、Other Penalty

你可以在一次保存中跨两个分组选择多个原因 — 例如 Red **Airways** 加上 Yellow **Under AP**。所选的标签按类别用颜色区分，因此你可以一眼看出正在记录什么。

Yellow 卡单独也支持多选（例如 Early Start + Grab）。Yellow 卡不会显示 Red 分组。

---

## Protests（申诉）

protest 是根据 AIDA Rulebook 17.8 提出的对某一结果的正式异议。Apnea Comp 会追踪整个流程 — 提交、选手的签名、jury 的裁决，以及对结果的任何更改。

**每个 protest 都以选手的签名结束**，即使是工作人员代选手发起的也是如此。

### 谁可以提交

Organizer、Main Judge、Judge 或选手本人。应用不追踪费用。

### 作为选手提交

> ![选手提交 protest](../images/protest-file.png)

1. Athlete Mode → **My Info** → 点按你结果旁边的 **File Protest**。
2. 输入原因，在屏幕上签名，然后提交。

> ![protest 签名板](../images/protest-sign.png)

protest 状态变为 **Pending** — 等待 jury。

### 代为提交（工作人员）

1. **Judge** 标签页 → 点按一张选手卡片 → **File Protest (on behalf)**。
2. 输入原因并提交。此时尚无签名。
3. protest 会以 **Awaiting signature** 状态发送给选手。选手在自己的手机上打开 **My Info**，查看后签名 — 只有这样它才会变为 **Pending**。

### Jury 裁决

> ![protest 列表](../images/protest-list.png)

打开 **More → Protests**（Organizer / Main Judge / Judge）。列表按状态对 protest 分组（Awaiting signature / Pending / Reviewing / Accepted / Rejected / Withdrawn）。点按其中一个进行裁决。

> ![protest 裁决界面](../images/protest-decide.png)

- **Accept** — 你可以修改结果（card、RP、remarks）。选手的记录会自动更新，更改会流转到 Results、Rewards 和 AIDA。
- **Reject** / **Withdraw** — 结果维持不变。

当 protest 仍处于 **Awaiting signature** 时无法裁决 — 选手必须先签名。

### Protest 投票

jury 通过 **匿名投票** 作出裁决：Judge 与 Main Judge 各自投 **Accept** 或 **Reject**。投票是匿名的 — 不会公开谁投了什么，只显示各项的计票数。

如果出现平票，由 **Main Judge** 以一票决定性（deciding）投票打破僵局。最终裁决表单要求 **Jury 签名**。

### 删除 protest

Organizer 或 Main Judge 可以从其详情界面（🗑 垃圾桶图标）删除任何 protest — 用它来清除测试条目，或清除卡在等待一个永远不会到来的签名上的遗留 protest。

### 通知

当 protest 被 **提交**、**等待签名** 或 **裁决** 时，所有工作人员和相关选手都会以各自选择的应用语言收到推送。

---

## Re-swim & Opener

### Re-swim

当 protest 被接受（或裁判要求重新表现）时，选手会再游一次。由于从 AIDA 加载某日的开始名单会替换当日的选手，re-swim 会先 **在队列中预留**，然后在构建目标日的名单时插入 — 这样它就绝不会被重新加载抹掉。

> ![预留 re-swim — 选择日期](../images/reswim-reserve.png)

1. **预留** — Judge / Main Judge / Organizer。在裁决 protest 时批准 re-swim，或为所选日期预留它（从日期下拉菜单中选择日期）。
2. **放置** — 当构建或加载该日的开始名单时，应用会提示：*「N re-swim(s) to place.」*。选择一种自动排序（AP 升序 / 降序 / 随机），或用 **Assign Lines** 手动放置每位选手（点按选手，然后点按目标 line 和位置）。如果 re-swim 在已加载的那一天，你可以立即放置它；否则，在 Setup → Add Athlete 下方有一个 **「Place pending re-swims」** 安全按钮。

> ![将 re-swim 放入开始名单](../images/reswim-placement.png)

3. **原条目被排除** — 原条目会被标记为 **invalidated**：从排名（Rewards）中排除，但仍显示在 Results 中。re-swim 的结果计入当日排名，并使用原始 start ID 推送到 AIDA。

### Opener

**opener** 是一个不应计入的热身或演示条目。Organizer / Main Judge 在 **Setup → Add Athlete** 下添加一个：姓名、nationality、gender、discipline、AP、PB（STA 使用 mm:ss 时间选择器；其他 discipline 使用数字）。Opener **被排除在排名之外，且绝不会发送到 AIDA**。

> ![Add Athlete 对话框（opener / 手动添加）](../images/add-athlete.png)

---

## 日程调整（OT Delay）

如果当天进度落后（热身过长、发生意外、设备问题），你可以在不重建开始名单的情况下推移剩余的 OT。

### 在哪里找到它

在 **Start List** 或 **Judge** 标签页中，AppBar 右侧的角色徽章前会显示一个 🕒 图标。**仅对 Organizer 和 Main Judge 可见。**

> ![OT Delay 图标位置](../images/ot-delay-icon.png)

### 如何使用

1. 点按 🕒 → **Adjust Schedule** 对话框打开。
2. 选择延迟的起点选手（OT 开始推移的第一位）。
3. 以 **分钟** 输入延迟（整分钟，仅正数）。
4. 预览会显示新的时间 — 每位受影响选手的 旧 → 新。
5. 点按 **Apply**。

从所选选手起的每个 OT 都会向前推移该数值。相应的 check-in / 热身时间也会一起推移。

### 副作用

- **推送通知** — 每位 OT 发生变化的选手都会收到自动推送：*「Your OT has been delayed by N minute(s)」*。他们无需订阅任何东西；通知仅针对受影响的选手定向发送。
- **活动日志** — 记录在 Log 界面中。

### 重要

- 仅支持正向延迟。无法提前。
- Undo **尚不可用** — 应用前请仔细查看预览。
- 所有工作人员的设备都会实时更新。

---

## 推送通知

Apnea Comp 使用推送通知来发送对时间敏感的赛事更新。通知通过 OneSignal 投递，OneSignal 再将其转发到 APNs（iOS）和 Firebase Cloud Messaging（FCM，Android）。每条通知都以接收者选择的应用语言发送。

### 会发送什么

有两种：你手动触发的通知，以及系统根据赛事状态自动发送的通知。

#### 手动（仅 Organizer / Main Judge）

从 More 菜单中，**Send Push** 会打开一个带三个按钮的小面板。每个都发送给所选日期已注册的所有选手：

- **Publish Start List** — 当当天的泳道和 OT 确定时。
- **Unofficial Results** — 发布初步结果供选手查看。
- **Official Results** — protest 窗口结束后的最终结果。

每次点按都会显示一个确认对话框，在发送前列出接收者数量。

#### 自动

这些无需工作人员操作即可运行：

| 触发 | 接收者 | 时机 |
|---------|-----------|------|
| OT Delay 已应用 | 仅受影响的选手 | Organizer / Main Judge 应用延迟后立即 |
| Check-in 截止提醒（1 小时） | 尚未签到的选手 | OT 前 2 小时（= check-in 截止前 1 小时） |
| Check-in 截止提醒（30 分钟） | 尚未签到的选手 | OT 前 1.5 小时（= check-in 截止前 30 分钟） |
| Protest 提交 | 所有赛事工作人员 + 该选手 | 当 protest 被提交时 |
| Protest 等待签名 | 所有赛事工作人员 + 该选手 | 当工作人员代选手提交时 |
| Protest 裁决 | 所有赛事工作人员 + 该选手 | 当 jury accept / reject / withdraw 时 |

一旦选手签到（或被标记为 DNS / Late），提醒就会停止。

### 谁会收到通知

仅同时满足以下所有条件的用户：

- 已关联的选手账户（上面的 Path A 或 Path B）
- 在操作系统层面启用了通知
- 在应用中启用了通知（默认：开）
- 一个有效的推送 token（在应用至少启动一次时创建）

### 关闭通知

- iPhone：设置 → Apnea Comp → 通知 → 关闭。
- Android：设置 → 应用 → Apnea Comp → 通知 → 关闭。
- 在应用中：More → About → 通知开关。

关闭会立即从服务器清除你的推送 token。

---

## 离线运行

应用被设计为在比赛进行中网络中断时仍能继续工作，这在泳池 / depth 场地很常见。

### 失去连接时会发生什么

顶部会出现一个红色条 **「You are offline」**。你仍然可以：

- ✅ 保存 Judge 结果（本地存储，稍后同步）
- ✅ 为选手 Check-in（本地存储，稍后同步）
- ❌ 从 AIDA 加载新的选手名单
- ❌ 接收推送通知（重新连接时投递，FCM 会保留它们）

### Offline 徽章

> ![选手卡片上的 Offline 徽章](../images/offline-badge.png)

当你在离线时保存结果，选手卡片会显示一个小的 **⛔ Offline** 徽章，而不是 AIDA 同步徽章。这表示：

- 结果在你设备的内存中是 **安全** 的。
- 它 **尚未** 到达服务器。
- 应用会在后台每 5 秒自动重试一次。

当网络恢复时，徽章会自动变为 **✅ AIDA**。无需手动操作。

### 手动同步

如果由于某种原因自动重试没有跟上，请打开 **Results**：

> ![Results 同步横幅](../images/results-banner.png)

如果有任何待处理项，你会看到一个橙色横幅：

- **「N offline result(s) waiting to sync」** 以及一个 **Sync now** 按钮 — 点按立即重试。
- **「M results not synced to AIDA」** 以及一个 **Resync** 按钮 — 用于 AIDA 一侧的失败（token、服务器错误等）。

### ⚠️ 重要

离线结果会一直存在于你的设备内存中，直到它们同步。**在有离线项待处理时，请勿强制关闭应用或重启手机** — 它们会丢失。请等待 ⛔ 徽章全部消失，或在退出前点按 Sync now。

如果你不确定，请打开 Results 并查找橙色横幅。没有横幅 = 没有待处理项。

---

## AIDA 集成

### 获取你的 token

在 <https://www.aidainternational.org> 登录你的 AIDA International 管理员账户。打开你注册的比赛。查找 API / Integration 部分以复制：

- **AIDA Token** — 看起来像一长串字母和数字。
- **AIDA Event ID** — 一个数字，通常为 4–6 位。

如果你看不到这些选项，则需要注册该赛事的 AIDA 管理员来分享它们，或者需要更新你的账户权限。

### 在应用中配置

Edit Event → 粘贴两个值 → Test Connection → Save。应用会将 token 安全地缓存在服务器上（绝不会在 URL 中暴露）。当你更新 token 时，新值会立即用于下一次保存（无需重启应用）。

### 同步什么以及何时同步

- **读取** — Setup → Load Athletes 拉取开始名单，包括姓名、AP、PB 和 discipline。
- **写入** — Judge 中的每次 Save 都会发送结果（RP、card、reasons、remarks、start offset）。后台进行，不阻塞。

### 同步失败时

- **Token 过期 / 无效** → 红色 SnackBar：*「AIDA token invalid — update in Edit Event」*（Organizer / Main Judge）或 *「ask Organizer to update」*（其他角色）。更新 token，然后 Results → Resync。
- **网络错误** → 卡片上的 🔁 Retry 徽章。点按它查看错误信息并重试，或使用 Results → Resync 一次性完成。
- **离线** → ⛔ Offline 徽章。在线时自动重试；参见 [离线运行](#离线运行)。

### Mock mode

将 token 设为 `test` 或 `demo`（或将两个字段都留空）即可在没有 AIDA 的情况下运行。应用会生成示例选手；不会发送任何内容。用于培训、演练或应用演示。Mock 模式的赛事会忽略真实世界的日期，因此倒计时和语音提示会立即工作以便测试。

---

## 多日赛事

对于跨越多日的比赛：

- Setup → **Total Days** → 设为比赛天数。
- 每一天都有自己的开始名单、check-in、结果和 OT。
- 当有不止一天时，AppBar 下方会出现一个 **Day selector**。点按以切换。
- **Rest days**：在 Setup 中标记它们；它们在排程中会被跳过。

数据 **不会** 在不同日之间结转 — 在 Day 2 移动选手不会影响 Day 1。跨日的总分在 Results 中计算。

如果你的赛事在 AIDA 上注册为多日，Load Athletes 会自动拉取每日的开始名单。

---

## 结果与导出

**Results** 标签页显示实时排名，随着判定的录入而更新。

- 顶部的 **摘要卡片**：选手总数、white / yellow / red、AP / PB / RP。
- **discipline 筛选** 以按项目缩小范围。
- 顶部的 **同步横幅**（如有）：Offline 待处理、AIDA 待处理或 token 问题。
- 按积分排序的 **选手列表**，点按查看详情。
- **Export** — 分享一份 CSV，用于张贴在公告栏或发送给选手。

### Rewards & 排名

**Rewards** 标签页（在 Athlete Mode 中也是一个标签页）按积分对选手排名，并按 discipline 和 gender 分组。

- **Day 标签** — Total、Day 1、Day 2 … 以界定排名范围。
- **Include yellow card scores** 开关。
- **Tiebreak**（右上 ⚙） — 拖动以重新排列 tiebreak 规则。AIDA 默认（Rulebook §4.2.16）为：total points → **AP−RP 差最小** → Red 更少 → Yellow 更少 → White 更多。完全相同者共享同一名次，下一名次跳过（**奥林匹克并列**，例：两个第 1 → 下一个是第 3）。深度 RP 以整数米输入（§4.1.22.1）。
- Opener 和 invalidated（已 re-swim）的条目会被排除在排名之外；所有人仍会出现在 Results 中。
- **Export CSV** — ↓ 图标分享一份 UTF-8 CSV（在所有语言中都能在 Excel / Numbers 中正确打开），反映当前的 Day / Yellow / Tiebreak 设置。

---

### Records (WR/CR/NR) — 记录

标记并确认世界 / 大洲 / 国家记录挑战。

1. **标记比赛** — 在创建或编辑比赛时，在 **Record Attempts** 中开启 **World Record** / **Continental**。之后比赛卡片和 Results 顶部会显示 🏅 徽章。
2. **检查记录** — 在 **Results** 标签点按 **Check WR/CR/NR**。对每位白卡选手，应用会按国籍、项目、性别查询 AIDA 官方记录并建议 WR / CR / NR。需要联网 — 无法获取的会跳过。
3. **确认** *(Organizer / Main Judge)* — 建议显示为虚线徽章（如「WR?」）。点按以确认等级或清除。已确认的记录显示为实线徽章，并包含在 CSV 导出中。

> 仅白卡（有效）成绩可作为记录。带罚分的成绩不能成为世界或大洲记录（Rulebook §10.2）。建议是将实现成绩（RP）与当前记录比较，最终由裁判决定。


## 显示 & 语言

这两项设置都在头像菜单（右上角）中，并会即时应用于整个应用。

### Theme

> ![Theme 选择器](../images/theme-picker.png)

点按你的头像 → **Theme** → 选择 **System default**、**Light** 或 **Dark**。

### Language

> ![Language 选择器](../images/language-picker.png)

点按你的头像 → **Language** → 选择 **System default**、**English**、**한국어**、**日本語**、**简体中文** 或 **繁體中文**。应用会立即切换并记住你的选择。

比赛标准术语在每种语言中都保持英文 — OT、AP、RP、PB、discipline 代码（STA、DYN、…）、WHITE / YELLOW / RED、角色名称和 Line — 这样来自不同国家的工作人员读到的是相同的标签。

---

## FAQ

### 工作人员的手机没电了 — 我会丢失他们的录入吗？

不会。他们保存结果后，结果会立即存储到服务器（如果离线则存储在他们的设备上）。同一赛事中的其他设备会立即看到该结果。即使他们的手机永久丢失，唯一有风险的也只是未同步的离线结果 — 而且只有在故障那一刻有任何待处理项时才会如此。

### 两个人正在查看同一位选手并保存不同的结果

最后保存的胜出。应用目前不会对并发编辑发出警告。请通过口头协调来避免这种情况 — 通常只有一名裁判录入某个特定结果。

### 某选手显示 AP / PB 但没有 startId — 为什么？

很可能他们是在 Mock mode 中添加的，或是在 AIDA 之外手动导入的。AIDA 同步需要 startId；这些选手的结果不会发送到 AIDA（不显示徽章）。他们仍会出现在 Results 中。

### 我更改了 AIDA token，但旧结果仍然失败

打开 Results → 如果横幅显示「Update token & resync」→ 点按它。待处理项会用新 token 重新发送。应用将凭据缓存在服务器上，并在你保存 Edit Event 时刷新缓存，因此无需重启应用。

### 签到期间网络中断会怎样？

签到会保存在本地，选手卡片会显示一个小的 ⛔「Offline」徽章。连接一恢复，签到就会自动（在 5 秒内）同步到服务器。选手无需再次签名。签名绘制本身不会被存储 — 它仅在当下用于视觉确认。

### 某选手收不到推送通知

常见原因：

- 该选手已注册但尚未关联到某条 AIDA 选手记录（未找到自动匹配，也未兑换 invite code）。没有这种关联，系统就不知道哪位选手是他们。
- 在操作系统层面通知被禁用。iPhone：设置 → Apnea Comp → 通知。Android：设置 → 应用 → Apnea Comp → 通知。
- 应用尚未在新设备上启动过 — 推送 token 在启动时签发。
- 该选手已被标记为 DNS / Late / 已签到（在这种情况下，签到提醒会有意停止）。

### 我可以删除赛事吗？

可以。Organizer 或 Main Judge 可以删除赛事 — 在赛事列表中滑动它，或使用 **Edit Event → Delete**。删除是永久性的，会移除该赛事的所有数据（选手、结果、日志、check-in 状态、protests）。文件存储中已生成的 protest PDF 在整赛事删除时不会被自动移除；如果你需要将它们清除，请联系我们。

### 某个 protest 卡在「Awaiting signature」上，而选手无法签名

这发生在当前签名流程之前创建的旧 protest 上。Organizer 或 Main Judge 可以打开 **More → Protests → 该 protest → 🗑** 并删除它。参见 [Protests → 删除 protest](#protests申诉)。

### 应用显示「Update required」界面，且不让我进入

你安装的版本低于运营者为现场使用设定的最低版本。从 App Store / Play Store 更新到最新版本，然后重新打开 — 应用会重新检查并放你通过。

### 我需要在比赛当天一直开着应用吗？

是的，在用于判定或签到的设备上。应用不会在后台运行。如果你切换到另一个应用，屏幕状态会被保留，但离线自动重试会暂停，直到你重新打开应用。

**应用会在每一个界面上阻止屏幕自动锁定**，因此你可以把设备放在桌上而它不会熄灭。正因如此，电量会比平常消耗得更快 — 对于全天赛事，请让设备一直接着充电器。

推送通知本身不需要应用处于打开状态 — 只要你允许了通知，即使应用关闭，iOS / Android 也会投递它们。

### 支持哪些设备？

iPhone（iOS 15+）和 Android（Android 9+）。平板可以使用，但布局针对手机进行了优化。

---

## 故障排查

### Judge 中出现「Could not save」红色 SnackBar

这表示应用甚至无法在本地存储结果 — 通常是因为选手已加载，但本地列表失去了同步。点按 **Reload**（Setup）并重试。为便于诊断，错误信息中包含 athlete ID 和当前计数。

### 「AIDA token invalid」一直出现

- 在 Edit Event 中确认 token 没有前导/尾随空格。
- 点按 Test Connection — 它成功吗？
- 如果 Test 失败：联系你的 AIDA 管理员签发一个新 token。
- 如果 Test 通过但保存仍失败：打开 Results → Resync。

### 应用显示「You are offline」但我明明在线

连接性检查会 ping 服务器。如果服务器短暂无法到达（罕见），或你的网络拦截了 Supabase URL（在酒店 / 公共 wifi 上不常见），指示器可能会保持红色。无论如何都试着保存一个结果 — 如果成功，指示器会在几秒内消除。

### OT Delay 图标不见了

检查：

- 你是否在 **Start List** 或 **Judge** 标签页（图标在其他标签页会隐藏）。
- 你的角色是否为 Organizer 或 Main Judge（其他角色看不到它）。
- 查看 AppBar 右侧，角色徽章的正前方。

### Line Assignment 之后日程看起来不对

OT 计算在保存时运行。如果你重新排序了选手但看到错误的 OT，向上滚动并再次点按 **Save** — 时间现在应当与顺序相符。如果仍不符，请附上截图联系我们。

### 某个团队成员卡在 Pending 上

打开 Users 标签页 → 找到他们的姓名 → 分配角色（Judge / Staff / …）。需要按每个赛事进行批准；批准不会在赛事之间结转。

### 我已经判定了选手，但 Results 界面是空白的

下拉刷新。如果仍为空白，切换到另一个标签页再切回。如果问题持续，请截图并联系我们 — 这不应该发生。

### 我换手机后推送通知不再工作

在新手机上登录并启动一次应用。新设备的推送 token 会替换你账户中的旧 token。旧手机将不再收到通知。

---

## 隐私与数据

有关 App 收集哪些数据、如何处理以及你的权利的完整详情，请参见 [隐私政策](https://elfreediving.github.io/aida-competition-privacy/zh/PRIVACY_POLICY)。

简要概述：

- **存储什么** — 你的账户邮箱、显示名称、个人头像（如果你上传了）、AIDA athlete UUID（如果你以选手身份注册）、推送通知订阅 ID（如果启用了通知），以及你录入的比赛数据（选手结果、check-in 状态、活动日志和 protests）。
- **Protest 签名** — 当提交 protest 时，选手（及 jury）手绘的签名 **会** 作为正式 protest 记录的一部分被存储，并嵌入到一份生成的 PDF 中。这是下面规则的唯一例外。
- **不存储什么** — 选手的联系方式、照片、出生日期、**check-in** 签名绘制（check-in 板仅用于视觉确认），或 AIDA 公开披露内容之外的任何个人标识符。
- **存储在哪里** — Supabase（目前为美国区域），静态加密，仅通过按赛事划分数据范围的 Row-Level Security 策略访问。推送通知经由 OneSignal 传输，OneSignal 再将其转发到 APNs（iOS）和 FCM（Android）。
- **AIDA tokens** — 加密，仅 Organizer / Main Judge 角色可访问，绝不会在 URL 中暴露，也不会在客户端内存中停留超过必要时间。
- **离线缓冲** — 离线时保存的 judge 结果仅存在于 App 的内存中，并在重新连接后数秒内同步。
- **本地设备存储** — **Remember email** 会将你的邮箱保存到标准本地存储（SharedPreferences / NSUserDefaults）。如果你启用 **Remember password**，它会将你的密码保存到设备的安全密钥库（iOS Keychain / Android EncryptedSharedPreferences），绝不会保存到我们的服务器。你的主题和语言选择也会保存在本地。登出或卸载即可清除已存储的凭据。

---

## 联系方式

如有 bug、问题或反馈：

- Email: lee33179@gmail.com

报告问题时，请包含：

- 设备型号和操作系统版本
- 应用版本（More → About）
- 如相关，请附截图
- 问题发生的大致时间（以便我们与日志匹配）

---

最后更新: 2026-06-02。
