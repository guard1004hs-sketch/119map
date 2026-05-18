# 📍 AR 위치 탐색기

> 증강현실로 주변 500m 내 GPS 위치를 표시하는 웹앱

## 🚀 GitHub Pages 배포 방법

### 1단계 — 저장소 생성
1. GitHub에서 새 저장소 생성 (예: `ar-location`)
2. 이 파일들을 모두 업로드하거나 push

### 2단계 — GitHub Pages 활성화
1. 저장소 → **Settings** → **Pages**
2. Source: **GitHub Actions** 선택
3. 자동으로 배포 시작됨

### 3단계 — URL 확인
배포 후 URL 형식:
```
https://[GitHub아이디].github.io/[저장소이름]/
```

### 4단계 — QR 코드 생성
위 URL을 아래 사이트에서 QR 코드로 변환:
- https://qr.io
- https://www.qrcode-monkey.com

---

## 📌 위치 데이터 수정 방법

`locations.json` 파일을 수정하세요:

```json
[
  {
    "name": "📍 장소 이름 (이모지 추가 가능)",
    "lat": 37.12345,
    "lon": 127.12345,
    "desc": "설명 (선택사항)"
  }
]
```

### 위도/경도 확인 방법
1. 구글 지도에서 원하는 위치 우클릭
2. 첫 번째 줄에 좌표가 표시됨 (복사 가능)

---

## 🔧 설정 변경

`index.html` 상단 JS 변수 수정:

| 변수 | 기본값 | 설명 |
|------|--------|------|
| `SEARCH_RADIUS` | `500` | 탐색 반경 (미터) |
| `LOCATIONS_URL` | `'locations.json'` | 위치 데이터 파일 경로 |

---

## ⚠️ 주의사항

- **HTTPS 필수**: GitHub Pages는 기본적으로 HTTPS 제공 (카메라/GPS 작동)
- **실외 권장**: GPS는 실내에서 정확도가 낮음
- **Android Chrome**: 가장 호환성 좋음
- **iOS Safari**: 방향 센서 추가 권한 팝업이 뜰 수 있음 (허용 필요)
- **위치 권한**: 브라우저에서 "이 사이트에 항상 허용" 설정 권장

---

## 📁 파일 구조

```
ar-location/
├── index.html          # 메인 앱
├── locations.json      # 위치 데이터 (수정하여 사용)
├── README.md           # 이 파일
└── .github/
    └── workflows/
        └── deploy.yml  # 자동 배포 설정
```
