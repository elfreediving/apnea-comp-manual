# Apnea Comp — 사용자 매뉴얼

**AIDA 대회 운영 시스템**

이 매뉴얼은 Apnea Comp으로 프리다이빙 대회를 운영하는 전 과정을 다룹니다 (셋업부터 결과까지). 앱 안의 Help (More → Help)는 빠른 참조용이고, 이 문서는 실제 운영 시나리오와 트러블슈팅을 포함한 더 자세한 가이드입니다.

5분만 시간이 있다면 아래 **빠른 시작**과 마지막의 FAQ를 읽으세요.

---

## 목차

1. [시작 전 준비](#시작-전-준비)
2. [빠른 시작](#빠른-시작)
3. [역할별 권한](#역할별-권한)
4. [이벤트 만들기 (Organizer)](#이벤트-만들기-organizer)
5. [이벤트 참여하기 (Staff)](#이벤트-참여하기-staff)
6. [Setup: 선수, 라인, OT](#setup-선수-라인-ot)
7. [체크인](#체크인)
8. [판정 입력](#판정-입력)
9. [페널티 (Rulebook 17.7)](#페널티-rulebook-177)
10. [스케줄 조정 (OT Delay)](#스케줄-조정-ot-delay)
11. [오프라인 운영](#오프라인-운영)
12. [AIDA 연동](#aida-연동)
13. [멀티데이 대회](#멀티데이-대회)
14. [결과 및 내보내기](#결과-및-내보내기)
15. [FAQ](#faq)
16. [문제 해결](#문제-해결)
17. [연락처](#연락처)

---

## 시작 전 준비

필요한 것:

- Apnea Comp 앱이 설치된 iPhone 또는 Android 기기
- 안정적인 인터넷 (운영 중에는 끊겨도 일부 동작 — [오프라인 운영](#오프라인-운영) 참조)
- AIDA International 계정 (공식 대회로 운영 시 — Organizer만 해당)
- Organizer는 대회의 **AIDA Token**과 **Event ID** 필요. 없으면 🧪 Mock 모드로 동작 (샘플 데이터, AIDA 미전송)

각 judge / staff는 본인의 기기를 사용하는 것을 권장합니다. 여러 명이 동시에 같은 이벤트에서 작업할 수 있고, 결과는 실시간으로 동기화됩니다.

---

## 빠른 시작

### Organizer (이벤트 생성자)

1. 앱을 열고 Events 화면에서 **+** 탭
2. 이벤트 이름, 종목 (Pool / Depth / Team), 날짜 입력 후 Create
3. 이벤트 진입 → **Edit Event** → **AIDA Token**과 **AIDA Event ID** 입력 → **Test Connection** 탭 → Save
4. Setup 탭 → **Load Athletes** 로 AIDA에서 선수 명단 가져오기
5. Setup 탭 → **Lines** (라인 수), **First OT**, **Interval** 설정
6. Edit Event에 표시된 **invite code**를 staff에게 공유
7. staff가 가입하면 **Users** 탭에서 승인 (처음엔 Pending 상태)

### Staff (judge, 체크인 담당 등)

1. 앱 로그인
2. Events 화면 → **Join with code** → invite code 입력
3. 처음엔 **Pending** 상태. Organizer가 승인하고 역할을 부여하면 (Judge / Main Judge / Staff 등) 이벤트 진입 가능

이제 운영 준비 완료입니다.

---

## 역할별 권한

| 역할 | Setup | Judge | Check-in | Users | Log | OT Delay |
|------|-------|-------|----------|-------|-----|----------|
| 👑 Organizer | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ⚖️ Main Judge | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ✏️ Judge | — | ✅ | ✅ | — | — | — |
| 👀 Staff | — | 보기만 | ✅ | — | — | — |
| ⏳ Pending | — | — | — | — | — | — |

- **Organizer**는 이벤트를 만든 사람의 기본 역할
- **Main Judge**는 Organizer와 동일한 권한. Users에서 부여
- **Pending**은 새로 가입한 멤버의 초기 상태. Organizer 또는 Main Judge가 Users에서 승인하고 역할을 줘야 작업 가능

---

## 이벤트 만들기 (Organizer)

### 기본 정보

- **이름** — staff에게 보이는 이름
- **종목** — 🏊 Pool, 🌊 Depth, 또는 👥 Team
- **날짜** — 멀티데이 이벤트는 시작/종료 날짜 선택

### AIDA 연동 (필수)

이벤트 진입 → **Edit Event** → 입력:

- **AIDA Token** — AIDA 관리자 페이지에서 발급
- **AIDA Event ID** — AIDA 대회의 숫자 ID

**Test Connection** 탭. 초록색 체크가 뜨면 토큰이 유효하고 선수 명단 조회 가능. Save.

> ![AIDA 필드가 있는 Edit Event 화면](images/edit-event-aida.png)

비워두거나 토큰을 `test`로 두면 🧪 **Mock 모드**로 동작 (샘플 선수 자동 생성). Mock 모드는 AIDA로 아무것도 보내지 않습니다 — 연습/리허설용.

### Staff 초대

invite code는 **Edit Event**에서 확인 가능. 일반적인 채널로 공유 (채팅, 이메일 등). Staff는 Events 화면의 **Join with code**로 입력.

> 팁: invite code 재발급은 아직 지원 안 됨. 비밀번호처럼 취급하고, 팀원에게만 공유하세요.

---

## 이벤트 참여하기 (Staff)

1. 앱 로그인
2. Events 화면에서 **Join with code** 탭
3. 코드 붙여넣기. 이벤트가 목록에 나타나며 **Pending** 상태
4. Organizer 승인을 기다림. 승인되면 이벤트 진입 가능

코드를 잘못 입력했다면 Organizer에게 Users에서 제거를 요청하고 다시 시도하세요.

---

## Setup: 선수, 라인, OT

> ![Setup 화면 구조](images/setup-screen.png)

### 선수 가져오기

- **Load Athletes** — AIDA에서 등록된 선수 명단 가져오기. 안전하게 여러 번 호출 가능 (기존 판정 결과 보존됨)
- **Mock 모드** — 샘플 선수 명단 생성

### 라인과 OT 설정

- **Lines** — 풀 라인 수 (Pool) 또는 플랫폼 라인 수 (Depth)
- **First OT** — 첫 선수가 시작하는 시각 (예: `09:00`)
- **Interval** — 같은 라인의 연속 선수 사이 간격 (분)
- **Depth Line Interval** (Depth만) — 다른 라인의 두 선수 사이 최소 간격. `(라인 수 − 1) × line interval < athlete interval` 조건을 만족해야 스케줄 생성 가능

### Line Assignment (라인 배정)

선수를 가져온 후 **Line Assignment** 화면에서 드래그로 라인 변경 / 순서 조정. OT는 자동 재계산:

- Pool: 라운드 로빈 배치, OT는 라인 내 위치에 따라 결정
- Depth: 전체 시퀀스 + 라인 순환, depth line interval 규칙 반영

저장하면 그날의 시작 시간이 확정됩니다.

---

## 체크인

선수가 워밍업 전 체크인합니다. **Check-in** 탭 진입.

- pending 상태의 선수 카드 탭 → 사인 시트 열림
- 선수가 화면에 사인 → **Save** 탭 → 체크인 시각 기록 완료
- 노쇼: 선수 탭 → **DNS** (Did Not Show) 확정
- 컷오프 후 도착: 선수 탭 → **Late Check-in**. 자동으로 Red 카드 + "Late Check-in" 비고 처리

> 체크인은 인터넷 필요. 오프라인이면 사인 단계에서 빨간 SnackBar로 실패 → 인터넷 복구 후 재시도. (Judge의 결과 저장은 오프라인에서도 동작하지만, 체크인은 아직 미지원.)
> 사인 그림은 시각적 확인용으로만 사용 — 체크인 순간 스태프에게 보여주고 시트가 닫히는 즉시 폐기됩니다. 사인 이미지는 어디에도 저장되지 않습니다.
---

## 판정 입력

> ![선수 카드가 있는 Judge 탭](images/judge-tab.png)

Judge 탭은 그날의 모든 선수를 표시. 카드 탭으로 결과 입력.

### 결과 입력 절차

1. **RP** — 실현 기록 (static은 시간, dynamic은 거리, depth는 깊이)
2. **Card** — White (정상), Yellow (페널티), 또는 Red (DQ)
3. **Penalty reasons** — White 외 카드 선택 시 필수. [페널티](#페널티-rulebook-177) 참조
4. **Start offset** — 빠른 (음수) 또는 늦은 (양수) 출발 초. 시작 시간 페널티 계산용
5. **REMARKS** — 일부 사유에서 필수 (BO, Other Penalty, DQ Other 등). 앱이 템플릿 자동 입력 → 누락된 부분만 작성
6. **Save Result** 탭

### 카드 배지

저장 후 선수 카드에 작은 배지 표시:

- **✅ AIDA** — AIDA International에 동기화 완료
- **🔁 Retry** — AIDA 동기화 실패. 탭하면 사유 확인 + 재시도
- **⛔ Offline** — 기기에 임시 저장됨. 인터넷 복구 시 자동 동기화. [오프라인 운영](#오프라인-운영) 참조

배지가 안 보이면 AIDA 연동이 설정 안 된 선수 (startId 없음) — Mock 모드에선 정상.

---

## 페널티 (Rulebook 17.7)

앱은 AIDA Rulebook 17.7 기준으로 동작. 사유는 카드 색상별로 분류.

### 🟨 Yellow card 사유

- **Start** — 잘못된 출발 동작 (Pool DYN: 벽 출발 실패 등)
- **Early Start** — OT 전 출발. 5초당 1점, 시작 윈도우 내
- **Late Start** — OT 후 출발. 5초당 1점, 시작 윈도우 내
- **Grab** — 라인, 벽, 또는 플랫폼을 잡음
- **Other Penalty** — 그 외 사유. **REMARKS 필수**

### 🟥 Red card 사유

- **Surface Protocol** — 부상 후 15초 내 잘못된 SP
- **Blackout Surface** — 수면에서 의식/운동 통제 상실. **REMARKS 필수** (회복 시간 등)
- **Blackout UW** — 수중 블랙아웃. **REMARKS 필수**
- **DQ Late Start** — Late Start이 시작 윈도우 초과 (Pool +10초, Depth +30초)
- **Jump Start** *(Pool DYN만)* — OT 전 벽 출발
- **DQ Other** — 그 외 실격 사유. **REMARKS 필수**

### 시작 윈도우

| 종목 | 윈도우 | 윈도우 내 | 윈도우 초과 |
|------|--------|-----------|-------------|
| Pool | ±10초 | 5초당 1점 (Yellow Early/Late Start) | 늦은 쪽 → DQ Late Start (Red); Pool DYN 벽 출발 빠름 → Jump Start (Red) |
| Depth | ±30초 | 5초당 1점 (Yellow Early/Late Start) | 늦은 쪽 → DQ Late Start (Red) |

### REMARKS

AIDA Rulebook 4.1.16.2는 모든 Yellow/Red에 대해 서면 사유를 요구합니다. REMARKS가 비어있으면 Save 버튼이 차단됩니다 (해당 사유에 한해).

사유 선택 시 REMARKS에 템플릿이 자동 입력됨 (예: `BO Surface, recovery: ___`). 누락된 부분만 채워서 저장 — 이게 공식 기록입니다.

Red 카드는 다중 선택 가능 (예: Surface Protocol + Blackout Surface). 해당하는 사유 모두 탭하세요.

---

## 스케줄 조정 (OT Delay)

운영 중 일정이 밀리면 (워밍업 길어짐, 사고, 장비 문제 등) 시작 명단을 다시 만들지 않고 남은 OT를 뒤로 밀 수 있습니다.

### 위치

**Start List** 또는 **Judge** 탭의 AppBar에 🕒 아이콘이 우측 (역할 배지 바로 앞). **Organizer / Main Judge만 보입니다.**

> ![OT Delay 아이콘 위치](images/ot-delay-icon.png)

### 사용 방법

1. 🕒 탭 → **Adjust Schedule** 다이얼로그 열림
2. 딜레이가 시작되는 첫 선수 선택 (이 선수부터 OT 변경)
3. 딜레이를 **분 단위**로 입력 (정수, 양수만)
4. 미리보기에서 영향받는 선수의 시간 변화 확인 (이전 → 새 시각)
5. **Apply** 탭

선택한 선수부터 끝까지 모든 OT가 그만큼 뒤로 밀림. 체크인/워밍업 시각도 같이 이동.

### 주의사항

- **양수 딜레이만 지원**. 시간 당기기 불가
- 모든 조정은 Log 화면에 기록됨
- **되돌리기는 아직 미지원** — 미리보기를 잘 확인하고 Apply
- 모든 staff 기기는 실시간 동기화

---

## 오프라인 운영

대회장은 풀/암반 환경이라 인터넷이 자주 끊깁니다. 앱은 이런 상황에서도 동작하도록 설계되었습니다.

### 인터넷이 끊겼을 때

화면 상단에 빨간 **"You are offline"** 띠가 표시됩니다. 이 상태에서:

- ✅ Judge 결과 저장 가능 (기기에 저장 후 나중에 동기화)
- ❌ 선수 체크인 불가 (인터넷 필요 — 복구 후 재시도)
- ❌ AIDA에서 새 선수 명단 가져오기 불가

### Offline 배지

> ![선수 카드의 Offline 배지](images/offline-badge.png)

오프라인에서 결과 저장 시 선수 카드에 작은 **⛔ Offline** 배지 표시 (AIDA 배지 대신). 의미:

- 결과는 기기 메모리에 **안전하게** 저장됨
- 아직 서버에 도달 **안 함**
- 앱이 5초마다 백그라운드로 자동 재시도

인터넷 복구 시 배지는 자동으로 **✅ AIDA**로 전환됩니다. 사용자 조작 불필요.

### 수동 동기화

자동 재시도가 실패한 경우 **Results** 화면 진입:

> ![Results 동기화 배너](images/results-banner.png)

대기 중인 항목이 있으면 주황색 배너 표시:

- **"N offline result(s) waiting to sync"** + **Sync now** 버튼 — 즉시 재시도
- **"M results not synced to AIDA"** + **Resync** 버튼 — AIDA 측 실패 (토큰, 서버 오류 등)

### ⚠️ 중요

오프라인 결과는 동기화될 때까지 기기 메모리에 있습니다. **대기 항목이 있는 동안 앱을 강제 종료하거나 폰을 재부팅하지 마세요** — 데이터 손실 위험. ⛔ 배지가 모두 사라질 때까지 기다리거나, 종료 전 Sync now 탭하세요.

확실하지 않으면 Results 화면을 열어 주황색 배너 확인. 배너 없음 = 대기 항목 없음.

---

## AIDA 연동

### 토큰 발급

<https://www.aidainternational.org> 의 AIDA International 관리자 계정으로 로그인. 등록한 대회 진입 후 API / Integration 섹션에서 복사:

- **AIDA Token** — 영문/숫자 긴 문자열
- **AIDA Event ID** — 4~6자리 숫자

이 옵션이 안 보이면 대회를 등록한 AIDA 관리자에게 공유 요청하거나 계정 권한 갱신 필요.

### 앱에서 설정

Edit Event → 두 값 입력 → Test Connection → Save. 토큰은 서버에 안전하게 캐싱 (URL에 노출 안 됨). 토큰 변경 시 다음 저장부터 즉시 새 값 사용 (앱 재시작 불필요).

### 무엇이 언제 동기화되는가

- **읽기** — Setup → Load Athletes로 선수 명단, 이름, AP, PB, 종목 가져옴
- **쓰기** — Judge에서 매 Save마다 결과 (RP, 카드, 사유, 비고, 시작 오프셋) 백그라운드 전송. 비차단

### 동기화 실패 시

- **토큰 만료/유효하지 않음** → 빨간 SnackBar: *"AIDA token invalid — update in Edit Event"* (Organizer / Main Judge) 또는 *"ask Organizer to update"* (그 외). 토큰 수정 후 Results → Resync
- **네트워크 오류** → 카드에 🔁 Retry 배지. 탭하면 오류 메시지 + 재시도, 또는 Results → Resync로 일괄 처리
- **오프라인** → ⛔ Offline 배지. 인터넷 복구 시 자동 재시도. [오프라인 운영](#오프라인-운영) 참조

### Mock 모드

토큰을 `test`로 설정 (또는 두 필드 모두 비움) → AIDA 없이 동작. 샘플 선수 자동 생성. AIDA로 아무것도 전송 안 함. 연습, 드라이런, 앱 데모용.

---

## 멀티데이 대회

여러 날에 걸친 대회:

- Setup → **Total Days** → 대회 일수 설정
- 각 날짜는 독립된 시작 명단, 체크인, 결과, OT
- 2일 이상이면 AppBar 아래에 **Day selector** 띠 표시. 탭으로 전환
- **휴식일**: Setup에서 표시 → 스케줄 생성 시 건너뜀

데이터는 날짜 간 **이동되지 않음** — Day 2의 선수 이동은 Day 1에 영향 X. 종합 점수는 Results에서 자동 계산.

AIDA에 멀티데이로 등록된 이벤트는 Load Athletes가 일자별 명단을 자동으로 가져옵니다.

---

## 결과 및 내보내기

**Results** 탭은 실시간 순위 표시. 판정 입력 시 즉시 갱신.

- 상단 **요약 카드**: 총 선수 수, white / yellow / red 수, AP / PB / RP
- 종목 필터로 좁히기
- (있는 경우) **동기화 배너**가 상단: Offline 대기, AIDA 대기, 토큰 문제
- 점수순 **선수 목록**, 탭하면 상세
- **Export** — CSV / 이미지 공유로 게시판 부착, 선수에게 전송

---

## FAQ

### Staff 폰 배터리가 다 떨어졌어요. 입력한 내용이 사라지나요?

아니요. 결과를 저장하는 즉시 서버에 (또는 오프라인이면 기기에) 저장되며, 같은 이벤트의 다른 기기는 즉시 결과를 봅니다. 폰을 영영 잃어버려도 위험한 건 그 순간 동기화 안 된 오프라인 결과뿐입니다 — 그것도 대기 중인 항목이 있을 때만요.

### 두 사람이 같은 선수를 동시에 다른 결과로 저장하면?

마지막 저장이 이깁니다. 앱이 동시 수정을 경고하지 않습니다. 보통 한 선수당 한 명만 입력하므로 운영 시 구두로 조율하세요.

### 선수에게 AP/PB는 있는데 startId가 없어요. 왜?

Mock 모드에서 추가됐거나 AIDA 외부에서 수동으로 가져온 경우입니다. AIDA 동기화는 startId가 필요하므로 그 선수의 결과는 AIDA로 전송 안 됩니다 (배지 없음). Results에는 정상 표시됩니다.

### AIDA 토큰을 바꿨는데 이전 결과는 계속 실패해요

Results 화면 진입 → 배너에 "Update token & resync" → 탭. 대기 항목이 새 토큰으로 재전송됩니다. 앱은 토큰을 서버에 캐싱하고 Edit Event 저장 시 캐시를 갱신하므로 앱 재시작 불필요.

### 인터넷이 없을 때 체크인이 실패했어요. 선수가 다시 사인해야 하나요?

네. 사인이 저장 안 됐습니다 (서버 확인 없이는 체크인을 받지 않음). 인터넷 복구 후 다시 사인 요청하세요.

### 이벤트를 삭제할 수 있나요?

현재 이벤트는 archive만 가능, 영구 삭제는 앱에서 안 됩니다. 삭제가 필요하면 (개인정보 / GDPR 등) 연락 주세요.

### 운영 중에 앱을 계속 열어둬야 하나요?

네, 판정/체크인에 사용하는 기기에서요. 앱은 백그라운드에서 동작 안 합니다. 다른 앱으로 전환하면 화면 상태는 보존되지만, 오프라인 자동 재시도는 앱을 다시 열 때까지 일시 중지됩니다.

### 어떤 기기를 지원하나요?

iPhone (iOS 15+) 와 Android (Android 9+). 태블릿도 동작하지만 레이아웃은 폰에 최적화.

---

## 문제 해결

### Judge에서 "Could not save" 빨간 SnackBar

기기에 결과 저장조차 안 된 경우 — 보통 선수 명단이 동기화 어긋났을 때. Setup → **Reload** 후 재시도. 오류 메시지에 진단용으로 선수 ID와 현재 명단 수가 포함됩니다.

### "AIDA token invalid"가 계속 떠요

- Edit Event에서 토큰 앞뒤 공백 확인
- Test Connection 탭 → 성공하나요?
- Test 실패 시: AIDA 관리자에게 새 토큰 발급 요청
- Test 성공인데 저장은 실패: Results → Resync

### "You are offline" 표시되는데 인터넷은 잘 돼요

연결 확인은 서버에 핑을 보냅니다. 서버가 일시적으로 안 잡히거나 (드물게) 호텔/공용 wifi가 Supabase URL을 차단하면 (보통은 안 그럼) 빨간 표시가 유지될 수 있습니다. 그래도 결과 저장을 시도해보세요 — 성공하면 몇 초 안에 표시가 사라집니다.

### OT Delay 아이콘이 안 보여요

확인:

- **Start List** 또는 **Judge** 탭에 있나요? (다른 탭에선 숨김)
- 역할이 Organizer 또는 Main Judge인가요? (다른 역할은 안 보임)
- AppBar 우측, 역할 배지 바로 앞을 확인

### Line Assignment 후 스케줄이 이상해요

OT 계산은 저장 시 실행됩니다. 선수 순서를 바꾸고도 OT가 잘못됐다면 위로 스크롤해서 **Save** 다시 탭 → 시간이 순서에 맞게 갱신됩니다. 그래도 이상하면 스크린샷과 함께 연락 주세요.

### 팀원이 Pending에서 안 바뀌어요

Users 탭 → 이름 찾기 → 역할 부여 (Judge / Staff 등). 승인은 이벤트별로 따로 받아야 하며, 다른 이벤트로 이월되지 않습니다.

### 판정한 선수가 있는데 Results 화면이 비어있어요

아래로 당겨서 새로고침. 그래도 비어있으면 다른 탭으로 갔다가 돌아오기. 계속 그러면 스크린샷과 함께 연락 주세요 — 정상 상황이 아닙니다.

---

## 개인정보 및 데이터

본 앱이 어떤 데이터를 수집하고 어떻게 처리하는지, 사용자의 권리에 대한 자세한 내용은 [개인정보처리방침](https://elfreediving.github.io/aida-competition-privacy/PRIVACY_POLICY)을 참조하세요.

요약:

- **저장하는 것** — 계정 이메일, 표시 이름, 프로필 사진 (업로드한 경우), 입력한 대회 데이터 (선수 결과, 사인, 활동 로그)
- **저장하지 않는 것** — 선수의 연락처, 사진, 생년월일, AIDA에서 공개한 정보 외의 개인 식별자
- **저장 위치** — Supabase (현재 미국 리전). 저장 시 암호화되며, Row-Level Security로 이벤트별 데이터 격리
- **AIDA 토큰** — 암호화 저장. Organizer / Main Judge 역할만 접근 가능. URL이나 클라이언트 메모리에 필요 이상으로 노출되지 않음
- **오프라인 버퍼링** — 오프라인에서 저장된 판정 결과는 앱 메모리에만 보관되며, 인터넷 복구 후 수 초 내 동기화

---

## 연락처

버그, 질문, 피드백:

- 이메일: lee33179@gmail.com

문제 보고 시 다음을 포함해주세요:

- 기기 모델과 OS 버전
- 앱 버전 (More → About — 곧 추가 예정)
- 관련 스크린샷
- 문제 발생 대략 시각 (로그와 매칭하기 위함)

---

*이 매뉴얼은 Apnea Comp 프로젝트의 일부입니다. 소스: <https://github.com/elfreediving/apnea-comp-manual>. 마지막 업데이트: 2026-05-03.*
