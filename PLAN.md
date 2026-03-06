# nullpoint.cloud 루트 도메인 포털 페이지 제작 계획

## 목적
- Google AdSense 사이트 인증을 위해 `nullpoint.cloud` 루트 도메인에 콘텐츠 필요
- 여러 서브도메인 프로젝트들의 메인 포털 역할
- **무료 + 24시간 상시 운영** (GitHub Pages 사용)

---

## 기술 스택
- HTML + CSS + JS (순수 정적 파일)
- **GitHub Pages** (무료 호스팅, 커스텀 도메인 + HTTPS 자동 지원)

---

## 디렉토리 구조
```
D:\Desktop\rootpage\
├── index.html       ← 포털 페이지 (AdSense 코드 포함)
├── style.css
├── ads.txt          ← AdSense 인증 필수
└── CNAME            ← nullpoint.cloud 입력 (GitHub Pages 커스텀 도메인용)
```

---

## 페이지 디자인 요구사항
- 라이트모드 기반의 모던한 포털/랜딩 페이지
- 상단: 로고 + `nullpoint.cloud` 타이틀
- 메인: 서브도메인 프로젝트 카드
  - 🐼 DevPanda — AI & 개발자 유틸리티 툴킷 → https://devpanda.nullpoint.cloud
- 하단: 심플한 푸터

---

## AdSense 코드 (`<head>`에 삽입 필수!)
```html
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-9370602153477675"
     crossorigin="anonymous"></script>
```

## ads.txt 파일 내용
```
google.com, pub-9370602153477675, DIRECT, f08c47fec0942fa0
```

## CNAME 파일 내용
```
nullpoint.cloud
```

---

## 배포 순서

### 1. GitHub 레포 생성
- GitHub에서 새 레포 생성 (예: `nullpoint-root`)
- `D:\Desktop\rootpage\` 파일들 push

### 2. GitHub Pages 활성화
- 레포 → **Settings → Pages**
- Source: `main` 브랜치 / `/ (root)` 선택
- Custom domain: `nullpoint.cloud` 입력

### 3. 가비아 DNS 설정
A 레코드 4개 추가 (이름: `@`, TTL: 600):
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

### 4. HTTPS 활성화
- GitHub Pages 설정에서 **"Enforce HTTPS"** 체크 (DNS 전파 후 자동 활성화)

---

## 완료 기준
- `https://nullpoint.cloud` 접속 시 포털 페이지 표시 + 자물쇠 🔒
- `https://nullpoint.cloud/ads.txt` 접속 시 내용 표시
- AdSense 콘솔에서 `nullpoint.cloud` 상태 승인
