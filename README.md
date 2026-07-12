# Designing AI Serving Systems (at Cloud Scale)

[![Build PDF](https://github.com/euiseong/TBB-ko/actions/workflows/build-pdf.yml/badge.svg)](https://github.com/euiseong/TBB-ko/actions/workflows/build-pdf.yml)
[![Latest PDF](https://img.shields.io/badge/download-latest%20PDF-2563EB)](https://github.com/euiseong/TBB-ko/releases/latest/download/main.pdf)
 
**Download the book:** [latest PDF](https://github.com/euiseong/TBB-ko/releases/latest/download/main.pdf) — 이 책의 최신 버전을 다운로드 받을 수 있습니다.
 

AI 서비스 밑바탕의 원리 — 가상화, 컨테이너, 쿠버네티스, 서빙 엔진, 그리고 비용 —
를 하나의 이야기로 엮은 오픈 교재입니다. 21시 04분에 무너진 데모에서 시작해,
의도한 대로 정확히 월 900달러에 운영되는 서비스까지.

> **저자:** 서의성 · 성균관대학교 교수
> **판본:** 한국어판 · 2026 · 원리에서 출발하는 교재

이 저장소는 책의 **LaTeX 소스**를 담고 있으며, 장(chapter)마다 디렉터리 하나로
구성돼 있습니다. (영어판은 [euiseong/TBB](https://github.com/euiseong/TBB)에 있습니다.)

---

## 책 구성

3부, 13개 장, 서문과 에필로그로 이루어져 있습니다.

**1부 — 인프라와 원리**
1. 과정 개요: AI 서비스의 큰 그림
2. 가상화 원리와 클라우드 컴퓨팅
3. 컨테이너 내부
4. Docker와 컨테이너 런타임 스택
5. Kubernetes
6. 스토리지와 네트워킹

**2부 — AI 서빙 시스템**
7. 서빙 시스템 입문
9. 모델 서빙 프레임워크
10. 추론 최적화
11. LLM 서빙
12. 스케일링과 비용 최적화

**3부 — 운영**
13. MLOps와 배포 자동화
14. 모니터링과 신뢰성

*(제8장은 중간고사에 해당해 별도의 장이 없습니다. 그래서 장 번호가 7에서 9로
건너뜁니다. 각 장 파일이 자기 번호를 직접 지정하므로 이 공백은 자체적으로
처리됩니다.)*

---

## 저장소 구조

```
main.tex                     마스터 파일: 문서 클래스, 앞부속, 3개 부, 각 장 \include
style/
  tbb.sty                    책 전체 스타일 — 팔레트, 폰트, 박스, 표, 제목
  tbb-fallback.tex           글리프 폰트 폴백 (본문 폰트가 없는 기호)
  tbb-codeactive.tex         코드 블록 안에서도 위 기호가 폴백되도록 처리
  tbb-dyncolors.tex          본문에 인라인으로 쓰인 추가 색상
frontmatter/
  titlepage.tex              표지
  preface.tex                "그 위의 계층"
chapters/
  ch01/ … ch14/              장마다 디렉터리 하나
    chNN.tex                 장 본문
    figures/                 그 장의 그림 (PNG)
backmatter/
  epilogue/
    epilogue.tex             "지루한 서비스"
    figures/
Makefile
```

각 장은 (절 단위로 쪼개지 않은) `.tex` 파일 하나와 그 장 전용 `figures/` PNG
디렉터리로 이뤄집니다.

---

## PDF 빌드

이 책은 **XeLaTeX**로 조판합니다(한글과 다량의 유니코드 — 화살표, 그리스 문자,
원문자, 박스 문자 등 — 를 사용합니다).

**필요 사항**

- XeLaTeX와 `latexmk`가 포함된 TeX Live (2022 이상).
- 폰트(모두 무료이며 리눅스에 대개 기본 설치돼 있음):
  - **Noto Sans CJK KR** (한글 본문 — 고딕)
  - **DejaVu Sans / DejaVu Sans Mono** (기호, 박스 문자, 코드)

  Debian/Ubuntu: `sudo apt install texlive-xetex texlive-latex-extra fonts-noto-cjk fonts-dejavu`

**빌드**

```bash
make            # latexmk -xelatex 실행 (목차 때문에 두 번 컴파일)
# 또는 직접:
xelatex main.tex && xelatex main.tex
```

결과물은 `main.pdf`(A4, 약 400쪽)입니다. `make clean`으로 빌드 부산물을 지웁니다.

---

## 편집

`chapters/`, `frontmatter/`, `backmatter/` 아래의 `.tex` 파일이 소스입니다 —
직접 편집하세요. 스타일은 `style/tbb.sty`에 모여 있어, 색·크기·박스를 한 곳에서
바꾸면 전체에 반영됩니다.

스타일이 제공하는 주요 빌딩 블록(장 본문에서 사용):

- `\section{…}` / `\subsection*{…}` — 번호 있는 절 규칙선과 회색 소제목
- `\namedsection{요약}{부제}` — 장 끝의 절(요약·연습문제 등)
- `\begin{calloutbox}{강조색}{배경색} … \end{calloutbox}` — 강조 박스
- `\begin{terminalbox}` + `\begin{Verbatim}…\end{Verbatim}` — 어두운 터미널
- `\qitem{n}{…}` — 번호 매긴 연습문제/정답 항목
- `\code{…}` — 인라인 고정폭

그림을 추가하려면 해당 장의 `figures/`에 PNG를 넣고
`\includegraphics{figures/그림.png}`를 쓰세요(검색 경로는 `main.tex`에 설정돼 있음).

한글은 본문 폰트가 모두 처리합니다. 본문 폰트에 없는 기호(새 기호·화살표 등)를
쓰면 `style/tbb-fallback.tex`에 한 줄(`\newunicodechar`로 `\symfont` 또는
`\cjkfont`에 매핑)을 추가하면 렌더됩니다.

---

## 그림

그림은 **PNG**로만 포함돼 있습니다. 각 장은 자기 그림을 `chapters/chNN/figures/`에
둡니다.

---

## 기여

수정과 개선을 환영합니다 — 이슈나 PR을 열어 주세요. 장별로 서식을 넣지 말고
`style/tbb.sty`에 스타일을 모아 주시고, 제출 전에 `make`로 빌드가 정상인지
확인해 주세요.

---

## 라이선스

[`LICENSE`](LICENSE) 참조 — 본문과 그림은 CC BY-NC-SA 4.0으로 배포됩니다.

---

## 저자

서의성 · 성균관대학교. 이 책이 어떻게 만들어졌는지는 서문 "그 위의 계층"에
담겨 있습니다.
