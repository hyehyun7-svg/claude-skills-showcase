# KakaoTalk 예약 메시지 일괄 등록 (kakao-schedule-runner)

카카오톡 데스크톱의 **메시지 예약** 기능으로 여러 날짜의 메시지를 한 번에 걸어둔다. 서버측 예약이라 PC를 꺼도 발송된다.

## 스킬 정의 (SKILL.md 상단)

| 항목 | 내용 |
|---|---|
| name | kakao-schedule-runner |
| description | Bulk-creates KakaoTalk scheduled messages (예약 메시지) in the desktop app for a date range — typically a month of daily reminders to a group chat — and audits existing reservations for duplicates, gaps, and wrong dates before adding anything. Works on both macOS and Windows KakaoTalk desktop. |

## 이 스킬이 이렇게 생긴 이유

두 가지 사고가 실제로 있었고, 절차 전체가 그걸 막도록 짜여 있다.

1. **채팅 입력창 경로는 오발송을 낸다.** 채팅 입력창에 문구를 타이핑하고 `+ → 메시지 예약`으로 들어가면, 예약을 건 뒤에도 초안이 입력창에 그대로 남는다. 이후 아무 클릭에서나 실제 전송이 터진다. 18명 단톡방에 자정 오발송이 이렇게 났다. 그래서 이 스킬은 브리핑 보드 경로만 쓴다.
2. **기존 예약은 이미 틀어져 있을 수 있다.** 사람이 손으로 넣어둔 예약에서 중복 2건과 누락 1건이 발견됐다. 확인 없이 새로 넣으면 중복 위에 중복을 얹게 된다. 그래서 감사가 등록보다 먼저다.

## 요약

- 한 달치 일일 알림 같은 반복 발송을 한 번에 예약합니다.
- 등록 전에 기존 예약의 중복, 누락, 날짜 오류를 점검합니다.
- macOS와 Windows 카카오톡 데스크톱에서 동작합니다.

상세 절차와 스크립트는 비공개 저장소에서 관리합니다.
