# Chapter 3 번역 검토 — 어색한 부분·번역투 목록

영어 원문(main.pdf)과 `chapters/ch03/ch03.tex`를 문단 단위로 대조한 결과. 줄 번호는 수정 전 ch03.tex 기준.

> **처리 현황 (2026-07-16):** A 전체(18건), B 전체(40건), C3·C4·C5·C6·C11·C12·C14 반영 완료(59개 행 수정).
> **보류(책 전체 정책 결정 필요):** C1 비공개(ch02·04·05·13 공용), C2 신원(ch01·13 공용), C8 뭉텅이(장 내 일관, 유지), C10 공급자(ch02 공용).
> **확인 후 유지:** C9 활성값(ch01·10·11도 동일 표기), C13 퇴거(ch05도 동일 표기).

---

## A. 오류 — 문법이 깨졌거나 뜻이 어긋난 곳 (우선 수정)

| # | 줄 | 현재 번역 | 원문 | 문제 / 제안 |
|---|----|----------|------|------------|
| A1 | 93 | "네임스페이스를 힌트로 추측해 그리고, §3.2의 setns와 비교해 보자" | Sketch a guess (namespaces are the hint); check it against §3.2's setns | 문장 파손. → "네임스페이스를 힌트 삼아 답을 그려 본 뒤, §3.2의 setns와 맞춰 보자" |
| A2 | 146 | "관점의 정직성은 마운트의 정직성만큼이다" | your view … is only as honest as your mounts | "~만큼이다"는 비문. → "Linux 시스템에 대한 관점은 마운트가 정직한 만큼만 정직하다" |
| A3 | 260 | "최선에는 … 최악에는" | Best case, … Worst case, | 비문. → "최선의 경우 … 최악의 경우" |
| A4 | 525 | "같은 그림이 두 번 실행된다" | the same plot runs twice | plot(줄거리)을 '그림'으로 오역. → "같은 이야기가 두 번 반복된다" |
| A5 | 525 | "요청을 차단할 수 있다" | you can shed the request | shed(떨궈서 부하를 덜다)를 '차단'으로 오역. → "요청을 떨궈 낼 수 있다" |
| A6 | 309 | "실제 위험에 얼마나 가까운지 알려 줄 파일을 쓰라" | name the file that would tell you… | "파일을 쓰라"가 '파일에 기록하라'로 읽힘. → "파일의 이름을 쓰라" |
| A7 | 199, 475 | "컨테이너화(containerization) 모델 서버", "컨테이너화 모델 서버" | a containerized model server | '~화된'이 빠져 어색 + 병기 단어도 잘못(containerized). → "컨테이너화된 모델 서버" |
| A8 | 386 | "이 순서는 과정 내내 값을 치르는 세 가지를 사 준다" | This ordering buys three things this course keeps paying for | 돈 은유가 꼬여 뜻이 반대로 읽힘(혜택인데 비용처럼). → "이 순서 덕분에 책 내내 두고두고 덕을 보는 세 가지가 생긴다" |
| A9 | 130 | "같은 커널 작업이" | The same kernel task | task는 커널 용어 '태스크'. '커널 작업'은 kernel work로 읽힘. → "같은 커널 태스크가" |
| A10 | 258 | "기간이 있는 하드 할당량" | a hard quota with a period | 스케줄링의 period는 '주기'. → "주기가 있는 하드 할당량" |
| A11 | 203 (그림 3-4 캡션) | "cpu.max는 부하를 뭉텅이로 스로틀링해" | cpu.max throttles in bursts | 목적어 오류 — 스로틀링 대상은 부하가 아니라 그룹. → "cpu.max는 뭉텅이 단위로 실행을 멈춰 세워" |
| A12 | 484 | "증거는 피해자 밖에만 존재한다" | the evidence lives entirely outside the victim | "밖에만"이 '피해자밖에(only)'로 오독됨. → "증거는 피해자의 바깥에만 남는다" |
| A13 | 258 | "남는 자원을 활용하므로 이를 강제하려고 사이클을 낭비하지 않는다" | It is work-conserving: no cycles are ever wasted to enforce it | 인과가 원문에 없고 work-conserving 의미가 왜곡. → "노는 자원을 놀리지 않는 방식이라, 이를 강제하느라 사이클을 낭비하는 일도 없다" |
| A14 | 260 | "p99는 창의 남은 시간에 가까운 배수로 뾰족하게 튀며" | p99 spiky in ~multiples of the window remainder | 뜻이 통하지 않음. → "p99는 창 잔여 시간의 대략 배수 단위로 튀며" |
| A15 | 531 | "무한한 메모리 동작이 제한되고" | turns unbounded memory behavior into bounded | unbounded는 '무한한'이 아니라 '상한 없는'. → "상한 없는 메모리 동작에 상한이 생기고" |
| A16 | 91 | "'컨테이너는 VM보다 가볍다'는 말에는 어떤 의미가 있는가?" | What does that imply about "containers are lighter than VMs" on a laptop? | imply 소실 — 앞 사실이 이 통념에 던지는 함의를 물어야 함. → "이 사실은 노트북 위에서 '컨테이너는 VM보다 가볍다'는 말에 어떤 함의를 갖는가?" |
| A17 | 150 | "…의무 두 가지를 부여한다. 컨테이너화되어 갑자기 자신이 PID 1이 되기 전까지는 그렇다." | two duties that most application code has never had to think about — until it gets containerized | "전까지는 그렇다"의 지시 대상이 모호(부여한다에 걸림). → "…생각해 본 적 없는 의무 두 가지를 부여한다 — 컨테이너에 담겨 갑자기 자신이 PID 1이 되기 전까지는." |
| A18 | 99 | "두 번째 커널도 나타나지 않는다. 그것은 제2장의 방식이었다." | no second kernel appears (that was Chapter 2's move) | 독립 문장이 되며 지시가 모호(네임스페이스가 2장 방식?). → "(두 번째 커널을 띄우는 것은 제2장의 방식이었다)" |

## B. 번역투 — 영어 관용구·구조가 그대로 비치는 곳

| # | 줄 | 현재 번역 | 원문 | 제안 |
|---|----|----------|------|------|
| B1 | 108, 605 | "긴 외투를 입은 setns" | setns() in a trench coat | 트렌치코트(변장) 밈이 한국어로 전달 안 됨. → "겉모습만 바꾼 setns" / "setns의 변장" |
| B2 | 534 | "BestEffort pod가 먼저 벽에 세워진다" | first against the wall | 총살 관용구가 직역돼 뜻 불명. → "가장 먼저 희생된다" (처형 모티프를 살리려면 "가장 먼저 처형대에 선다") |
| B3 | 80 | "모든 일의 바닥에는 이 장의 세 메커니즘이 있다" | bottoms out in this chapter's three mechanisms | → "결국 이 장의 세 메커니즘으로 귀결된다" |
| B4 | 77 | "레시피 관점은 이 책의 매주 운영에서 보상을 준다" | the recipe view pays off operationally, every week | → "레시피 관점은 이 책 내내 매주 운영 현장에서 값을 한다" |
| B5 | 81 | "실전에서 가장 흔한 서빙 장애가 이 장의 결말이다" | The most common serving outage in the wild is this chapter's finale | 장애=결말 구조가 어색. → "이 장의 대미를 장식하는 것은 실전에서 가장 흔한 서빙 장애다" |
| B6 | 82, 386, 475 | "가장 큰 단일 항목", "가장 흔한 단일 방식" | the single largest line / the single most frequent way | 'single' 직역. → "단일 항목으로는 최대" / "단연 가장 흔한 방식" |
| B7 | 43 | "이국적인 객체가 튀어나오는 것이 아니다" | no exotic object springs into being | exotic=이국적 아님. → "신기한 객체가 튀어나오는 것이 아니다" (73줄 "새로운 종류의 물체"도 → "새로운 종류의 무언가") |
| B8 | 152, 484 | "롤링 배포를 재생해 보자", "규칙을 시간 순서로 재생해 보자" | play the tape / replay as a timeline | '재생'은 미디어 재생으로 읽힘. → "…가 어떻게 흘러가는지 돌려 보자" / "시간순으로 되짚어 보자" |
| B9 | 152 | "영구적이고 자초한 장애 생성기다" | a permanent, self-inflicted outage generator | → "스스로 만들어 배포 때마다 돌아가는 장애 제조기다" |
| B10 | 169 | "새 비공개 스택은 새로 연결이 끊긴 스택이기도 하다" | A freshly private stack is also a freshly disconnected one | → "갓 만든 전용 스택은 아직 아무 데도 연결되지 않은 스택이기도 하다" |
| B11 | 186 | "악명 높게 도움 되지 않는 ERROR: …와 함께 죽는다" | dies with a notoriously unhelpful ERROR | 부사 직역. → "아무 도움도 안 되기로 악명 높은 오류 …와 함께 죽는다" |
| B12 | 186 | "그 플래그가 어느 네임스페이스에 말하는지 안다" | which namespace that flag is talking to | → "그 플래그가 어느 네임스페이스를 향한 것인지 안다" |
| B13 | 274 | "전체 이야기를 제2장의 스틸 타임 옆에 기록하자" | File the whole story next to Chapter 2's steal time | → "이 이야기는 제2장의 스틸 타임과 나란히 기억해 두자" |
| B14 | 278 | "벽에 이르는 길에는 단순한 그림이 놓치는 정거장이 있다" | the path to the wall has a stop the naive picture misses | '정거장'이 생경. → "벽에 이르는 길에는 순진한 그림이 놓치는 중간 기착지가 하나 있다" 또는 "…놓치는 단계가 하나 있다" |
| B15 | 282 | "빈 공간에도 주목해야 한다" | Note also the negative space | → "없는 것에도 주목해야 한다" |
| B16 | 282 | "4주 차에 도구의 배관을 보여 준다" | Week 4 shows the toolkit plumbing | → "4주 차에 툴킷의 내부 배관을 들여다본다" |
| B17 | 505 | "자세히 읽으면 보상받는 세부 사항이 있다" | one detail that rewards close reading | → "자세히 읽은 보람이 있는 세부 사항이 하나 있다" |
| B18 | 509 | "무상태 웹 앱으로 훈련한 직관이 오해하는 형태" | a shape that intuition trained on stateless web apps gets wrong | → "무상태 웹 앱만 다루며 길러진 직관이 잘못 짚는 형태" |
| B19 | 52 | "운영체제 첫 과목부터 사용한 일반 프로세스 도구" | tools you have used since your first OS course | → "첫 운영체제 수업 때부터 써 온 평범한 프로세스 도구" |
| B20 | 426 | "다시 가리키기와 교체하기의 차이는 이제 익힌 고전적인 컨테이너 보안 각주다" | Repoint versus replace: the classic container-security footnote, now yours | '이제 익힌…각주다' 연결 어색. → "다시 가리키기냐 통째로 갈아 끼우기냐 — 고전적인 컨테이너 보안 상식 하나가 이제 당신 것이 되었다" |
| B21 | 533 | "해결책 대화는 '…'여야 하며" | The fix conversation is … | → "해결을 논의할 때 나와야 할 말은 '…'이지 '…'가 아니다" |
| B22 | 534 | "Kubernetes 번역을 알아둔다" | Know the Kubernetes translation | '번역'이 혼동 유발. → "쿠버네티스에서 무엇이 무엇에 대응하는지 알아둔다" |
| B23 | 316 | "읽기 전용 lower 디렉터리 여러 개(…), 쓰기 가능한 upper 디렉터리 하나(…)를 컨테이너가 /로 마운트하는 하나의 merged 관점으로 제공한다" | several read-only lower directories…, one writable upper directory…, presented as a single merged view | 연결어 누락으로 파싱 곤란. → "…여러 개와 …하나를 **겹쳐**, 컨테이너가 /로 마운트하는 하나의 merged 뷰로 제공한다" |
| B24 | 169 | "구체적으로 -p 8080:8000으로 공개한 8000번 포트의 컨테이너까지 노트북의 요청 하나를 추적해 보자" | trace one request from your laptop to a container serving on port 8000, published with -p 8080:8000 | 어순 꼬임. → "노트북에서 출발한 요청 하나가 -p 8080:8000으로 공개된 컨테이너의 8000번 포트에 닿기까지를 따라가 보자" |
| B25 | 587 | "이번 주에는 클라우드 계량기가 없지만" | No cloud meter this week | → "이번 주에는 과금될 클라우드 자원이 없지만" |
| B26 | 739 | "커널 문서치고 유난히 잘 썼으며" | unusually well-written for kernel documentation | 주어 불일치. → "커널 문서치고는 유난히 잘 쓰인 글로" |
| B27 | 258 | "네이티브 최고 속도로 실행되다가" | runs at full native speed | → "제 속도 그대로 내달리다가" |
| B28 | 278 | "이후 전체 이야기를 그 절이 맡는다" | which owns the full story from here | → "자세한 이야기는 그 절이 도맡는다" 정도로 완화 |
| B29 | 12 | "실제 메모리 사용 형태를 수치로 고려해" | for an inference server's real memory shape, with numbers | → "실제 메모리 사용 형태를 수치와 함께 따져" |
| B30 | 484 | "파일을 많이 쓰는 단계는" | file-heavy phases | '쓰는'이 write로 오독됨. → "파일 I/O가 많은 단계는" |
| B31 | 110 | "숫자가 같을 때, 그리고 그때에만" | if and only if | 수학 교과서 직역. 유지해도 되나, 산문이라면 → "숫자가 같으면 같은 네임스페이스, 다르면 다른 네임스페이스다 — 예외는 없다" |
| B32 | 186 | "가장 작은 네임스페이스이자 최고의 교사다" / "고고학적 각주처럼 들리지만" | the best teacher / an archaeology footnote | → "가장 작지만 가장 많이 가르쳐 주는 네임스페이스다" / "호랑이 담배 피우던 시절 각주처럼 들리지만" |
| B33 | 731 | "cgroup도 Docker의 부상보다 오래되었다" | cgroups predate Docker's rise | → "cgroup 역시 Docker가 뜨기 전부터 있었다" |
| B34 | 395 | "올바른 계층에서는 배포마다 몇 바이트가 이동하는가?" | With proper layering, how many bytes move per deploy? | → "올바르게 계층화하면 배포마다 몇 바이트가 이동하는가?" |
| B35 | 552 | A부 첫 문장 — 아티팩트 4개를 한 문장(7행)에 담아 중첩 괄호로 나열 | (원문도 길지만 영어는 세미콜론으로 지탱) | 한국어에서는 문장 분리 필요. 아티팩트별로 4문장 권장 |
| B36 | 41 | "약간 도발적으로 들리도록 만든 주장으로 시작한다" | a claim designed to be slightly scandalous | → "일부러 약간 도발적으로 벼린 주장으로 시작한다" |
| B37 | 173 | "목적지를 …으로 다시 쓴다" | rewrites the destination | → "목적지를 …으로 고쳐 쓴다" |
| B38 | 462 | "이 장을 구성으로 번역한 것처럼 읽힌다" | reads like this chapter translated into configuration | '구성'보다 '설정'이 자연스러움. → "이 장을 설정 파일로 옮겨 적은 것처럼 읽힌다" |
| B39 | 388 | "불변 시연 이미지나 엣지 장치에서는" | immutable demo images, edge appliances | → "불변 데모 이미지나 엣지 장비에서는" |
| B40 | 548 | "비싼 인스턴스도 위험하지 않다" | no expensive instance is at risk | → "비싼 인스턴스를 걸 필요가 없다" |

## C. 용어 — 일관성 확인 또는 선택 재고

| # | 항목 | 현황 | 비고 |
|---|------|------|------|
| C1 | private → **비공개** | 책 전체 관례 (ch02·04·05·13에서도 사용) | ch3만 고치면 안 됨. 다만 "비공개 관점/스택/루트"는 '기밀'처럼 읽힘 — 책 전체에서 "전용/자기만의"로 바꿀지 **정책 결정** 필요 |
| C2 | identity → **신원** (110, 124, 130) | ch01·13에도 등장 | 프로세스에 '신원'은 사람 냄새가 강함. "식별자"(inode 문맥) / "정체"(두 신원→두 얼굴) 검토 |
| C3 | referee → 3.3절 제목 "**중재**"(280) vs 3.6절 "**심판**"(473) | ch3 내부 불일치 | 3.6과 그림 3-4가 '심판'이므로 280줄도 "cgroup이 심판을 볼 수 있는 것과 없는 것"으로 통일 권장 |
| C4 | wiring → "연결"(10) vs "배선"(169, 462) | ch3 내부 불일치 | "배선"으로 통일 권장 |
| C5 | signature → "특징"(260) vs "서명"(525, 707) | ch3 내부 불일치 | 진단 문맥이므로 "정후" 또는 "특유의 흔적" 권장, 최소한 하나로 통일 |
| C6 | OOM kill → "OOM 강제 종료"(12, 475 등) vs "OOM kill"(309, 310, 520) | 혼용 | "OOM 강제 종료"로 통일 권장 |
| C7 | course → "이 책"(대부분) vs "**과정** 내내"(386) | 혼용 | "이 책"으로 통일 |
| C8 | in bursts → "**뭉텅이**로" (203, 258, 291, 613) | ch3 전용 표현, 내부적으론 일관 | 유지 가능하나 "한꺼번에 몰아서/통째로 멈추는"이 더 표준적. 결정 사항 |
| C9 | activations → "활성값" | ch3 | ML 한국어 관례는 "활성화 값". 9~11장과 맞출 것 |
| C10 | vendor → "공급자"(282, 703) | — | "벤더" 또는 "제조사" 권장 ("공급자 중립적"→"특정 업체에 매이지 않는") |
| C11 | 520줄 수식 내 영어 잔존 | "limit = idle + 10%", "measured worst spike × 1.25 headroom" | 수식이라 의도일 수 있으나 "측정한 최악 급증 × 1.25 여유"처럼 번역 가능. 결정 사항 |
| C12 | 연습문제 어미 혼용 | "~제시하라/쓰라"(683~) vs "~설명한다/논증한다"(693, 695, 697) | 명령형 "~하라"로 통일 권장 |
| C13 | evicted → "퇴거"(660) | — | K8s 한국어 문서는 "축출" 사용. 5장과 맞출 것 |
| C14 | "라우팅 테이블(routing table)"(167) | 이 단어만 영어 병기 | 주변 용어와 병기 기준 통일 |
| C15 | task → "커널 작업"(130) | A9와 동일 | "태스크"로 |

---

## 총평

전반적으로 원문의 문학적 문체(은유, 의인화, 아포리즘)를 성실하게 옮겼고 기술 내용의 누락은 발견되지 않았다. 문제는 대부분 (1) 영어 관용구의 축자역이 한국어에서 이미지가 성립하지 않는 경우(trench coat, first against the wall, play the tape, negative space), (2) 영어 통사 구조를 유지하다 생긴 비문·모호문(A2, A3, A12, A17), (3) 용어 흔들림(C3~C7)이다. A 목록 18건은 의미 훼손이므로 우선 수정을 권한다.
