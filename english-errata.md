# English Edition Errata — found during KO translation review

Issues in the English original (euiseong/TBB) discovered while cross-checking the Korean translation against `main.pdf`. The Korean edition already reflects the corrections noted below.

## 1. ch05 — "ready-but-unrouted" vs "Running-but-unrouted"
- **Where:** Chapter 5 learning objectives vs §5.6 body.
- **Issue:** The learning objective calls the failure state "ready-but-unrouted", while §5.6 names the same state "Running-but-unrouted". One name should be used consistently.
- **KO edition:** follows §5.6's naming.

## 2. ch06 — file storage price multiple: 10× vs 4×
- **Where:** Chapter 6 summary vs the storage-pricing table and body text.
- **Issue:** The summary states file storage costs "~10× block price"; the table and body both support ~4×.
- **Suggested fix:** change the summary to ~4×.
- **KO edition:** corrected to 약 4배.

## 3. ch09 — Markdown asterisks leaked into Further Reading
- **Where:** Chapter 9, Further Reading, the M. Nygard *Release It!* entry.
- **Issue:** Raw Markdown emphasis markers (`*...*`) survive in the typeset text around the entry, breaking the formatting.
- **Suggested fix:** replace with proper bold/italic markup.
- **KO edition:** re-set as `\textbf{M. Nygard, \textit{Release It!} (2판, 2018)의 안정성 패턴 장}`.

## 4. ch10 — retry-storm waveform attributed to Chapter 7
- **Where:** Chapter 10, §10.4 (torch.compile discussion): "the retry-storm waveform from Chapter 7".
- **Issue:** The retry-storm waveform is introduced and demonstrated in Chapter 9 (§9.5), not Chapter 7.
- **Suggested fix:** "from Chapter 9".
- **KO edition:** kept faithful to the original pending upstream fix.

## 5. ch12 — Figure 12-6 referenced but missing
- **Where:** Chapter 12. Figure captions jump from Figure 12-5 to Figure 12-7; §12.6 Part B deliverables reference "Figure 12-6's waterfall with your numbers".
- **Issue:** Figure 12-6 (the portfolio/ledger waterfall) is absent from the chapter body, though the asset `fig12-6_portfolio.png` exists in the repo. The waterfall numbers actually appear in Transcript 12-6.
- **Suggested fix:** either place Figure 12-6 in §12.5 with a caption, or change the §12.6 reference to "Transcript 12-6".
- **KO edition:** reference changed to 터미널 기록 12-6.

## Note (verify intentional, not an error)
- The Week-15 "Next week" box at the end of Chapter 14 contains Korean text inline ("팀 프로젝트 발표와 시연") in the English edition. Presumably intentional (course deliverable name); flagging only for confirmation.
