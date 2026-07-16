# Chapter 14 번역 검토

영어 원문(main.pdf)과 `chapters/ch14/ch14.tex` 대조 결과. ch03~13 방침 기준선 적용.

> **처리 현황 (2026-07-16):** A·B 전체 반영.
> **총평:** 두 시기에 나눠 번역한 흔적이 뚜렷함. §14.2·14.3·요약·연습문제·해설은 한국어 역어가 완전히 정착된 상급 번역(지표/대시보드/호출/티켓/소진율/감시 지표/데드맨 스위치…)이나, **§14.1·14.4·14.5·14.6에는 영어 일반명사가 대량 미번역 잔존**(probe, log, page, ticket, alert, alarm, queue, dashboard, panel, runbook, registry, postmortem, drill, window, burn, sentinel, stack, model, input, eval, judge…). 후반부·요약이 확정한 역어로 전면 정리.

## A. 대량 수정 (영어 잔존 → 확정 역어)

| 부류 | 대표 매핑 (요약·해설·§14.2가 확정한 역어 기준) |
|---|---|
| 경보 체계 | alert/alarm→경보, page→호출, pager→호출기, ticket→티켓, window→구간, burn (rate)→소진율, budget→(오류) 예산, rotation→로테이션, receiver→수신기, heartbeat→심장박동, dead man's switch→데드맨 스위치, cheat sheet→요약표 |
| 관측 | dashboard→대시보드, panel→패널, probe→프로브(활성 프로브=ch05), synthetic probe→합성 프로브, log→로그, metric→지표, stack→스택, scrape→스크레이프, query→질의, sentinel→감시 지표, trace→트레이스 |
| 운영 | runbook→런북, registry→레지스트리, postmortem→사후 분석, on-call→온콜, drill→훈련, incident note→사고 메모, action item→조치 항목, uptime checker→가동 확인기 |
| 드리프트 | model→모델, input→입력, eval set→평가 세트, slice→슬라이스, gate→게이트, judge→판정기, reference→기준, bin→빈(bin), feature→특징, embedding→임베딩, centroid→중심, anomaly detection→이상 감지, vendor→공급업체, lever→수단, ice house→얼음 창고, valley→골짜기 |
| Apollo | capsule→캡슐, crew→승무원, guidance computer→유도 컴퓨터, powered descent→동력 하강, simulation→시뮬레이션, abort→중단, executive→실행기, overload→과부하, telemetry→텔레메트리, signature→징후(ch03 확정) |
| 서빙 | queue→대기열, seat→좌석, admission→입장(ch11; 해설의 "허용 (선)"도 입장으로), retry storm→재시도 폭풍, waveform→파형, storm→폭풍, completion→완성, hang→멈춤, door→관문(ch06; 문/출입구도 관문으로 통일), turn→턴, token→토큰(산문) |

## B. 교차 장 용어·표기 정합

| # | 항목 | 조치 |
|---|---|---|
| B1 | course 자기 지칭 "이 강좌"(11곳) | → "이 책" ("마이크로서비스 강좌"=외부 강좌라 유지, "강의계획서"=수업 인프라 유지) |
| B2 | "무릎점"(2곳)·영어 "knee"(2곳) | → "굴곡점" |
| B3 | "시분할"(3곳)·"time-slice/slicing"(산문 7곳) | → "시간 분할" (ch02·12 확정) |
| B4 | "실행 터미널 기록"(5곳) | → "터미널 기록" (전 장 표기) |
| B5 | "N장"(무접두 장 번호 ~40곳), "N주차"(8곳) | → "제N장", "N주 차" |
| B6 | "릴리스 세 요소"(해설 1곳) | → "릴리스 삼중항" (ch13 확정) |
| B7 | "임계값"(2곳) | → "임곗값" (책 다수 표기·표준 표기) |
| B8 | "알람"(1곳) | → "경보" |
| B9 | 요약 제목 "열여섯 가지로 정리한 이 장", 장 구성 제목 "이 장의 구성" | → "열여섯 가지 핵심 내용", "장 구성" (ch11~13 형식) |
| B10 | 생각해 보기 어미: §14.2·14.3 박스는 "~하라", §14.1·14.4·14.5·14.6 박스는 "~하자" 혼재 | → 장 내 "~하라" 통일 |
| B11 | ch13 L578 인용 "TTFT는 정직한가? 행동이 드리프트했는가?" vs ch14 첫 문장 "TTFT가 정직한가? 행동이 drift했는가?" | 두 곳을 "TTFT는 정직한가? 동작이 드리프트했는가?"로 일치 (ch13 가드레일=동작 확정; ch13 수정은 교차 장 커밋에 포함) |
| B12 | ch12 인용 "SLO 아래의 time-slicing은…" | ch12 실제 문구 취지에 맞춰 "SLO 아래의 시간 분할은…" |

## C. 유지·참고

- "Apollo is the syllabus in miniature" → "이 강의계획서의 축소판"(의미 정확, 붙여쓰기만 수정).
- 원문 자체 특이점: 영어판 15주 차 박스에 한국어 "팀 프로젝트 발표와 시연"이 원문 그대로 포함되어 있음(수업용 이중 언어 표기로 보임) — 오류 아님.
- 고유 명칭 유지: SCE to Aux, 1202/1201, Power Peg류 코드·명령·PromQL·경보 이름(SLOBurnFast 등), Verbatim 블록 내 영어 주석 전체.
- "당직자"(§14.3)와 "온콜"(영어 on-call 치환) 병존 — 둘 다 자연스러운 한국어라 문맥별 유지.
