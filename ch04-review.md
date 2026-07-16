# Chapter 4 번역 검토 — 어색한 부분·번역투 목록

영어 원문(main.pdf)과 `chapters/ch04/ch04.tex`를 문단 단위로 대조한 결과. 줄 번호는 수정 전 ch04.tex 기준. ch03 검토에서 정한 방침(이 책, OOM 강제 종료, 징후, 의식적 등)을 기준선으로 삼았다.

> **처리 현황 (2026-07-16):** A 전체(9건), B 전체(19건), C1·C2 반영 완료. C3(공급자→공급업체, ch03 쪽 수정)은 별도 커밋.
> **보류(책 전체 정책):** "터미널 기록"(ch04) vs "기록"(ch03) — Transcript 번역 통일 필요, "따뜻한 플릿/노드"(warm) — 유지 판정(원문도 은유), "구호"(catchphrase).

---

## A. 오류 — 마크업 파손·의미 왜곡 (우선 수정)

| # | 줄 | 현재 번역 | 원문 | 문제 / 제안 |
|---|----|----------|------|------------|
| A1 | 629 | `/dev/nvidia\textit{ 장치 노드를 컨테이너에 넣고 cgroup }장치 허용 규칙*으로` | Device nodes /dev/nvidia* … with a cgroup *device allow rule* | **LaTeX 마크업 파손** — `\textit{}`가 엉뚱한 구간을 감싸고 `*`가 밖에 남음. → `\code{/dev/nvidia*} 장치 노드를 컨테이너에 넣고 cgroup \textit{장치 허용 규칙}으로` |
| A2 | 121 | 소제목 ""바로 아래 계층"이라는 말보다 더 중요한 이유" | Why serving engineers care — beyond "it's the next layer down" | 의미 어긋남(비교 대상이 뒤틀림). → "서빙 엔지니어가 관심을 가져야 하는 이유 — "바로 아래 계층이니까"를 넘어" |
| A3 | 111 | "하루 수십억 번" | a billion times a day | 수치 부풀림 + ch03 "하루에 10억 번"과 불일치. → "하루 10억 번" |
| A4 | 124 | "바이트 단위로 제5장이 스케줄링하고" | is, byte for byte, the artifact Chapter 5 schedules | '바이트 단위로 스케줄링'으로 오독됨. → "바이트 하나까지 똑같이" |
| A5 | 482 | "10초의 유예 시간 전체를 멈춰 있다가 SIGKILL된다" | hangs the full 10 s grace and gets SIGKILLed | 서버는 멈춘 게 아니라 신호를 무시하고 버티는 것. → "10초의 유예 시간을 꽉 채워 버티다가" |
| A6 | 461 | "제6장은 문의 장부(상태 코드, 대상 상태)를 읽는다" | Chapter 6 read the door's (status codes, target health) | "문의(問議)"로 오독됨. ch06은 "관문" 사용. → "관문의 장부" |
| A7 | 639 | "(제3장의 빈 공간을 메커니즘으로 설명)" | (Ch. 3's negative space, now mechanistic) | ch03 수정("없는 것")과 어긋난 교차 참조. → "(제3장의 공백을 메커니즘으로 설명)" |
| A8 | 350 | "Kubernetes는 같은 내용을 imagePullSecrets 참조로 필요로 한다" / "정적 비밀 없이도" | Kubernetes needs the same material as an imagePullSecrets reference / no static secret | 문장 어색 + secret 번역이 523줄 "풀 시크릿"과 불일치. → "Kubernetes에는 같은 자격 증명을 imagePullSecrets 참조로 건네야 한다" / "정적 시크릿 없이도" |
| A9 | 42, 660 | "쿠버네티스가", "제5장 쿠버네티스" | Kubernetes | 장 내 다른 곳과 5장 제목(`\chapter{Kubernetes}`)은 영문. → "Kubernetes"로 통일 |

## B. 번역투 — 직역·어색한 표현

| # | 줄 | 현재 번역 | 원문 | 제안 |
|---|----|----------|------|------|
| B1 | 126 | "GPU 절은 이후 모든 내용의 하중을 받는다" | The GPU section is load-bearing for everything after | → "GPU 절이 이후 모든 내용을 떠받친다" |
| B2 | 248 | "하중을 받는 설계 선택은 콘텐츠 주소 지정이다" | Content-addressing is the load-bearing choice | → "이 구조의 무게를 떠받치는 설계 선택은 콘텐츠 주소 지정이다" |
| B3 | 611 | "shim은 실행 중 데몬이 하중을 받지 않게 하려고 존재한다" | so the daemon is not load-bearing at runtime | → "shim은 실행 중에 데몬이 하중을 떠받치는 부품이 되지 않게 하려고 존재한다" |
| B4 | 117 | "shim이 있어 이후 프로세스를 맡는다" | the shim that owns it afterwards | '이후 프로세스'가 "나중 프로세스들"로 오독. → "shim이 있어, 이후 그 프로세스를 책임진다" |
| B5 | 162 | 소제목 "shim이 존재 가치를 입증하다" | The shim earns its keep — live | → "shim이 제 밥값을 하는 모습 — 실시간 확인" |
| B6 | 280 | "다단계 빌드는 실제 긴장을 해결한다" | Multi-stage builds resolve a genuine tension | → "다단계 빌드는 실재하는 딜레마를 해결한다" |
| B7 | 280 | "제3장의 탈출 결과 교훈을" | Chapter 3's escape-consequence lesson | 명사 나열. → "컨테이너 탈출의 피해를 줄이는 제3장의 교훈을" |
| B8 | 287 | 소제목 "GPU 버전: …" | The GPU flavor: … | 'GPU 버전'이 CUDA 버전과 혼동됨. → "GPU판: 가격표가 붙은 CUDA 태그 동물원" |
| B9 | 398 | "문장에 이제 기계실이 생겼다" | now has its machine room | → "문장의 기계실을 이제 들여다보았다" |
| B10 | 400 | "이제 강의계획서의 왜가 남는다" | Which leaves the syllabus's why | → "이제 강의계획서가 물었던 왜가 남는다" |
| B11 | 400 | "커널 가시적 "GPU 시간" 단위" | no kernel-visible unit of "GPU time" | → "커널에 보이는 "GPU 시간" 단위" |
| B12 | 454 | "우선 인증해 진정시키고" | Authenticate as triage | → "우선 인증으로 급한 불을 끄고, 장기적으로는 …" |
| B13 | 127 | "여기의 실패는 …" | Failures here look like magic… | → "이 계층의 실패는 …" |
| B14 | 67 | (더 읽을거리 포인터 누락) | …is this week's fun read — see Further Reading | → 문장 끝에 "(더 읽을거리 참고)" 복원 |
| B15 | 63 | ""온보딩"이라는 위키에서 서서히 썩어 갔다" | decaying in a wiki labeled "onboarding" | → ""온보딩"이라는 제목의 위키 문서 속에서 서서히 썩어 갔다" |
| B16 | 639 | "보상할 핵심 흐름은" | The through-line to reward | 채점 문맥. → "점수를 줄 핵심 흐름은" |
| B17 | 184 | "제3장을 설정 형식으로 번역해 놓은 것처럼" | reads like Chapter 3 translated into configuration | ch03 수정과 통일. → "옮겨 적은 것처럼" |
| B18 | 319 | "레지스트리는 놀랄 만큼 단순하다" | A registry is a deceptively simple thing | 뉘앙스 소실. → "레지스트리는 겉보기에는 맥 빠질 만큼 단순하다" |
| B19 | 14 | "레지스트리를 의도적으로 운영한다" | Operate registries deliberately | '의도적'은 딴 뜻 냄새. ch03·L306의 "의식적" 계열로. → "의식적으로 운영한다" |

## C. 용어 — 일관성

| # | 항목 | 현황 | 조치 |
|---|------|------|------|
| C1 | course → **과목/강의** 혼재 (117, 119, 124, 204, 248, 257, 425, 461, 474, 521, 593, 646) | 책 방침은 "이 책"(기존 커밋 참고). "강의 전에"(37, 실제 강의)와 "강의계획서"(syllabus)는 유지 | **적용** — 자기 지칭만 "이 책"으로 |
| C2 | Worked example → "풀이 예제"(125, 289, 292) | ch03은 "계산 예시" | **적용** — "계산 예시"로 통일 ("풀이 예제: 풀 시간…"의 풀-풀 중복도 해소) |
| C3 | vendor → ch04·05·10·13 "공급업체", ch03 "공급자"(2곳) | ch03이 소수파 | **별도 커밋** — ch03 두 곳을 공급업체로 |
| C4 | Transcript → ch03 "기록", ch04 "터미널 기록" | 다수파는 "터미널 기록"(ch01·04~09·14) | **해결** — 책 전체를 "터미널 기록"으로 통일 (커밋 6248f21, ch02·03·10~14의 93곳) |
| C5 | warm → "따뜻한 플릿/노드"(340, 359, 523) | 원문도 은유(warm fleet) | **유지** — 어색하다고 판단되면 "웜 플릿" 일괄 치환 가능 |
| C6 | "비행 기록 장치"(445) | ch05도 동일 표현 사용 | **유지** (일관) |

---

## 총평

ch04는 ch03보다 번역 품질이 좋다. 다만 (1) L629의 LaTeX 마크업 파손이 조판을 깨뜨리는 유일한 치명타이고, (2) "이 책" 방침이 이 장에는 적용되지 않아 과목/강의가 12곳 남았으며, (3) load-bearing("하중을 받는") 계열 직역이 3곳 반복된다. 교차 참조(제3장의 빈 공간, 문의 장부, 쿠버네티스 표기)는 ch03 수정 및 ch05·06 실제 용어와 맞춰 정리했다.
