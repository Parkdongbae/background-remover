# 배경제거 — 브라우저 AI 배경 제거 웹앱

이미지에서 AI로 배경을 제거하는 웹앱입니다. **모든 추론은 브라우저 안에서** 실행되며
이미지는 서버로 전송되지 않습니다.

## 품질 옵션

| 옵션 | 모델 | 특징 |
|---|---|---|
| 초정밀 | RMBG-1.4 (fp16) | 받침대·인공 구조물 보존에 강함 (비상업 라이선스) |
| 고화질 | ISNet (fp32) | 가장 느림, ISNet 최대 정밀도 |
| 표준 | ISNet (fp16) | 기본 권장 |
| 경량 | ISNet (int8) | 빠름 |

공통 기능: 원본·결과 비교 슬라이더, 배경 색상 프리셋, 수정 브러시(지우개/복원),
AI 경계 다듬기(편집 영역 크롭 재추론), PNG 다운로드.

> 이 저장소는 웹 배포용입니다. 로컬 Photoshop 자동화("PS 고정밀")는
> 데스크톱 전용 기능으로 이 배포에는 포함되지 않습니다.

## Vercel 배포

1. GitHub에서 이 저장소를 Vercel로 Import (또는 `npx vercel --prod`)
2. 추가 설정 불필요 — `vercel.json`에 COOP/COEP 헤더(ONNX 멀티스레드 활성)와
   `/models/*`, `/onnxruntime-web/*` 경로 재작성이 포함되어 있습니다

## 라이선스

- 앱 코드: MIT
- `@imgly/background-removal` + ISNet 모델: AGPL-3.0 (이 저장소로 소스 공개)
- `onnxruntime-web`: MIT
- RMBG-1.4 가중치: BRIA AI 비상업 라이선스 — 상업적 사용 시 별도 라이선스 필요

자세한 내용은 [LICENSE-NOTES.md](LICENSE-NOTES.md)를 참고하세요.
