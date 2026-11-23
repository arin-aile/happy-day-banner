# Happy Day 생일 배너 메이커

인물 사진 한 장을 올리면 MediaPipe로 누끼를 따고, 고른 스타일로 A3 비율(2100×2970px) 생일 축하 배너를 그려 주는 웹앱입니다.

- GitHub Pages: https://arin-aile.github.io/happy-day-banner/
- 아티팩트: https://claude.ai/artifact/Txyc7S1yGgNuaxvSV7dgGY
- 스타일 5종: 무대·청량 / 큐트·키치 / 힙·레트로 / 매거진·잡지 / 청순·청춘
- 누끼: MediaPipe Image Segmenter(자동 인식), Interactive Segmenter(클릭 지정)
- 얼굴 보호: MediaPipe Face Detector로 얼굴 위치를 찾아 장식이 얼굴을 가리지 않게 배치
- 배치 편집: 배너 위에서 인물·제목 드래그, 크기 슬라이더
- 사진은 서버로 보내지 않고 브라우저 안에서만 처리합니다.
- 이미지 생성 AI는 쓰지 않습니다. 배경과 장식, 글자는 모두 캔버스 코드로 그립니다.

## 로컬 실행

```bash
python3 -m http.server 8765 --directory app
```

브라우저에서 http://localhost:8765 를 엽니다.

## 구성

- `app/index.html` — 페이지 전체 (UI, 템플릿 렌더러, MediaPipe 연동)
- `app/mp/` — MediaPipe tasks-vision 0.10.21 번들과 모델 (아티팩트 배포 제약 때문에 모델 파일 확장자를 `.wasm`으로 바꿔 두었고, 인물 모델은 두 조각으로 나눴습니다)
- `app/fonts/` — Pretendard Variable (SIL OFL)
- `app/thumbs/` — 스타일 선택 썸네일
