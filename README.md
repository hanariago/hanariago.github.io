# hanariago.github.io (루트)

`hanariago.github.io` 호스트 루트 — **검색엔진 등록·검증 전용** + 도구 모음(hub)으로 안내.
(허브 자체는 `tools-hub` repo. 여기는 허브가 아님.)

## 구성
```
hanariago.github.io/
├── index.html        ← 랜딩 (도구 모음으로 링크) + 소유확인 메타 자리
├── robots.txt        ← 호스트 전체 robots (이 위치만 유효) + Sitemap 지정
├── sitemap.xml       ← 사이트맵 인덱스 (전체 tool-* sitemap 묶음)
└── <indexnow-key>.txt ← IndexNow 키 파일
```

## 왜 루트인가
- robots.txt는 **호스트 루트에서만** 읽힘 (`/tool-xxx/robots.txt`는 무시됨)
- GSC URL-prefix `https://hanariago.github.io/` 한 속성이 **모든 `/tool-xxx/` 하위를 커버**
- IndexNow 키 파일이 루트에 있으면 **호스트 전체 URL** 제출 인증
- 사이트맵 인덱스 1개 제출 = 전체 도구 sitemap 일괄

## 검색엔진 등록 (소유확인 코드는 Lena가 발급)
- **Google Search Console**: URL 접두어 `https://hanariago.github.io/` → HTML 태그 → `content` 값을 index.html 주석 자리에 추가
- **네이버 서치어드바이저**: 사이트 `https://hanariago.github.io/` → HTML 태그 → 마찬가지로 index.html에 추가
- **Bing**: GSC 인증 후 Webmaster Tools에서 Import (코드 불필요)
- 인증·sitemap 제출 후 → 새 도구 배포 시 IndexNow 핑으로 색인 요청

## 새 도구 추가 시
`sitemap.xml`(인덱스)에 새 도구 `tool-xxx/sitemap.xml` 한 줄 추가 + 커밋.

---
Made by Lena · License: MIT
