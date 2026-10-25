# nullpoint.cloud — 방안 A (실제 GLB 모델 + WebGL Fluid 셰이더 + 중앙 박스 제거) 체크리스트 (task.md)

- [x] **Step 0: 기본 골격 및 프로토타입 검증 완료**
- [x] **Step 1: Sector 01 업그레이드 — 중앙 블랙박스 제거 + WebGL Navier-Stokes 유체(잉크) 시뮬레이션 셰이더 적용** 🛑
  - [x] `FOR [블랙박스] TODAY`에서 중앙 블랙박스 및 3D 토러스 캔버스를 제거하고 순수 타이포그래피 레이아웃으로 정리
  - [x] `#ink-canvas`를 2D 원형 파티클에서 **진짜 WebGL GLSL 2D Fluid Simulation (Velocity/Curl/Pressure/Dye FBO 파이프라인)**으로 교체하여 마우스 이동 시 먹물/연기가 물리적으로 소용돌이치며 퍼지도록 구현
- [x] **Step 2: Sector 02~04 업그레이드 — 실제 `final-scene.glb` 전시관 모델 적용 + 천장 하강 & 우측 90° 시점 회전 연동** 🛑
  - [x] `assets/models/final-scene.glb` 및 `assets/beam_linear.png` 에셋 배치, Three.js `GLTFLoader` + `DRACOLoader` 연동
  - [x] 원본 레퍼런스와 동일한 라이트맵/베이킹 머티리얼(`map` + `emissiveMap`, `toneMappingExposure: 0.82`), 볼류메트릭 빛 기둥(`ConeGeometry`), 스크린 텍스처(`DevPanda`, `FolioSquad`) 적용
  - [x] 스크롤 시 **천장 하강(`rotation.x: 1.5 → 0`) → 우측 90° 카메라/전시관 시점 회전**으로 `1/2 DevPanda` → `2/2 FolioSquad` → `Likes & Visitor Stats` 전환 구현
- [x] **Step 3: 로컬 브라우저 시각 검증 및 Step 4 GitHub Pages 배포 준비** 🛑
- [x] **Step 4: Git 커밋 & `origin/main` 푸시 완료**
