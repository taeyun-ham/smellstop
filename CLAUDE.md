# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

**냄새는 못 참지** — 100% 천연 탈취제를 제공하는 B2B 악취제거 전문기업의 공식 웹사이트입니다.

- **기술 스택**: 순수 HTML, CSS, JavaScript (바닐라 JS, 프레임워크 무)
- **배포**: 정적 파일 호스팅 (HTML/CSS/JS 기반)
- **반응형**: 모바일 / 태블릿 / 데스크톱 완전 지원

## 아키텍처

### 페이지 구조

```
index.html       — 메인 홈 + 인사말 (회사소개 > 인사말)
location.html    — 오시는길 (카카오맵 임베드, 연락처, 교통 안내)
business.html    — 사업소개 (개요, 제거 가능 악취, 주요 고객, 서비스, 투자비용, 마케팅)
products.html    — 제품소개 (카테고리 탭 필터, 검색, 상세 모달)
css/style.css    — 전체 사이트 스타일
images/          — 페이지별 히어로 이미지
```

### 스타일 시스템

**CSS 변수** (`--primary`, `--secondary` 등)로 그린 계열 디자인 테마 관리:

- `--primary`: #2ecc71 (메인 그린)
- `--secondary`: #1a3c34 (다크 그린)
- `--accent`: #f0faf4 (배경 강조)
- 폰트는 pretendard 로 한다.

각 HTML은 `<style>` 태그로 페이지별 커스터마이징 포함 (특히 products.html의 탭 스타일, 모달 등).

### 주요 인터랙션

- **공통**: 상단 고정 헤더 + 드롭다운 네비게이션, 모바일 햄버거 메뉴 (JavaScript 토글)
- **제품소개**: 카테고리 탭 필터, 실시간 키워드 검색, 제품 상세 모달 (모두 바닐라 JS)

### 코드 스타일

- **코멘트**: 한국어 작성
- **변수/함수명**: 영어 유지 (코드 표준)
- **커밋 메시지**: 한국어 작성

## 주의 사항

- **CSS 통합**: `style.css`가 전역 스타일, 각 HTML의 `<style>` 태그가 페이지별 커스터마이징 담당 → 수정 시 어느 파일인지 확인
- **이미지**: `images/` 폴더의 4개 히어로 이미지 (hero-home.jpg, hero-business.jpg 등)는 각 페이지에서 배경으로 사용
- **카카오맵 API**: location.html에서 임베드 코드만 있고 실제 API 키 연동 미완료
- **제품 데이터**: products.html의 JavaScript 배열로 관리 (DB 무, 정적 데이터)

## 미구현 기능

README.md의 "미구현 / 추후 추가 권장 기능" 섹션 참고 (고객 후기 갤러리, 문의 폼, 블로그, SEO 최적화 등).
