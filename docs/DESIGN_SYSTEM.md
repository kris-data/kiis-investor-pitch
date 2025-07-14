# KiiS 프레젠테이션 디자인 시스템

## 📋 목차
1. [개요](#개요)
2. [공통 디자인 원칙](#공통-디자인-원칙)
3. [네비게이션 시스템](#네비게이션-시스템)
4. [팝업 시스템](#팝업-시스템)
5. [애니메이션 가이드라인](#애니메이션-가이드라인)
6. [슬라이드별 특화 사항](#슬라이드별-특화-사항)
7. [개발 가이드라인](#개발-가이드라인)
8. [체크리스트](#체크리스트)

---

## 개요

KiiS 투자자 프레젠테이션을 위한 통합 디자인 시스템입니다. 모든 슬라이드에서 일관된 사용자 경험과 전문적인 프레젠테이션 품질을 보장합니다.

### 핵심 목표
- **일관성**: 모든 슬라이드에서 동일한 UX/UI
- **접근성**: PC, 모바일, 키보드 모든 환경 지원
- **몰입감**: 방해받지 않는 프레젠테이션 경험
- **전문성**: 투자자들에게 신뢰감 제공

---

## 공통 디자인 원칙

### 🎨 색상 체계
```css
/* 기본 배경 */
background: radial-gradient(ellipse at center, #1e40af 0%, #0f172a 70%, #000000 100%);

/* 주요 색상 */
--primary-gold: #ffd700;
--primary-blue: #1e40af;
--secondary-blue: #1d4ed8;
--success-green: #10b981;
--warning-orange: #f59e0b;

/* 텍스트 색상 */
--text-primary: #ffffff;
--text-secondary: #e0e7ff;
--text-accent: #ffd700;
```

### 📐 레이아웃 원칙
- **컨테이너**: `max-width: 1400px, margin: 0 auto`
- **패딩**: 데스크톱 `60px 80px`, 모바일 `40px`
- **그리드 간격**: 기본 `40px`, 모바일 `30px`
- **카드 간격**: `20px-40px` (콘텐츠에 따라 조정)

### 🎯 타이포그래피
```css
/* 제목 */
.title { font-size: 48px; /* 모바일: 36px */ }
.section-title { font-size: 32px; /* 모바일: 24px */ }
.card-title { font-size: 24px; /* 모바일: 20px */ }

/* 본문 */
.body-large { font-size: 18px; }
.body-medium { font-size: 16px; }
.body-small { font-size: 14px; }
```

---

## 네비게이션 시스템

### 🎛️ 구조
모든 슬라이드에 동일하게 적용되는 통합 네비게이션 시스템

#### HTML 구조
```html
<!-- 네비게이션 호버 감지 영역 -->
<div class="hover-zone" id="hoverZone"></div>

<!-- 네비게이션 -->
<div class="navigation" id="navigation">
    <a href="[prev-slide].html" class="nav-btn prev">Back</a>
    <a href="[next-slide].html" class="nav-btn next">Next</a>
</div>
```

#### CSS 스타일
```css
.hover-zone {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 120px;
    z-index: 998;
    pointer-events: auto;
}

.navigation {
    position: fixed;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 20px;
    background: rgba(0, 0, 0, 0.9);
    padding: 15px 30px;
    border-radius: 50px;
    backdrop-filter: blur(15px);
    border: 2px solid rgba(255, 215, 0, 0.3);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    opacity: 0;
    visibility: hidden;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    z-index: 1000;
}

.navigation.visible {
    opacity: 1;
    visibility: visible;
}
```

### 🖱️ 상호작용 방식

#### PC (데스크톱)
1. **호버존 감지**: 화면 하단 120px 영역
2. **마우스 추적**: 전체 화면에서 마우스 위치 감지
3. **네비게이션 호버**: 네비게이션 자체 호버 시 유지
4. **주기적 확인**: 1초마다 마우스 위치 검증

#### 모바일 (터치)
1. **하단 터치**: 화면 하단 120px 터치 시 표시
2. **좌우 스와이프**: 50px 이상, 300ms 이하 스와이프
3. **화면 탭**: 빈 영역 탭으로 토글

#### 키보드
- `←/↑`: 이전 슬라이드
- `→/↓/Space`: 다음 슬라이드  
- `N`: 네비게이션 토글
- `ESC`: 네비게이션 숨김 + 팝업 닫기
- `Tab`: 네비게이션 5초간 표시

### 🔧 JavaScript 핵심 함수
```javascript
// 4가지 안전장치 구현
// 1. 호버존 이벤트
// 2. 마우스 위치 추적  
// 3. 네비게이션 호버
// 4. 주기적 위치 확인

const isTouchDevice = 'ontouchstart' in window || navigator.maxTouchPoints > 0;
```

---

## 팝업 시스템

### 🪟 구조
```html
<!-- 오버레이 -->
<div class="overlay" id="overlay" onclick="hideSource()"></div>

<!-- 팝업 -->
<div class="source-popup" id="sourcePopup">
    <button class="close-btn" onclick="hideSource()">×</button>
    <div id="sourceContent"></div>
</div>
```

### 🎨 스타일
```css
.source-popup {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: rgba(0, 0, 0, 0.95);
    color: white;
    padding: 40px;
    border-radius: 20px;
    border: 2px solid #ffd700;
    max-width: 700px;
    max-height: 80vh;
    overflow-y: auto;
    z-index: 1000;
    backdrop-filter: blur(10px);
    display: none;
}
```

### 📝 콘텐츠 구조
```javascript
const sources = {
    'source-id': {
        title: '팝업 제목',
        content: `
            <p><strong>섹션 제목:</strong></p>
            <p>설명 내용</p>
            <ul>
                <li><strong>항목:</strong> 세부 내용</li>
            </ul>
        `
    }
};
```

---

## 애니메이션 가이드라인

### 🎬 로딩 애니메이션 원칙
1. **순차적 등장**: 논리적 순서로 요소 등장
2. **자연스러운 타이밍**: 200-300ms 간격
3. **부드러운 트랜지션**: `cubic-bezier(0.4, 0, 0.2, 1)`
4. **네비게이션 힌트**: 로딩 완료 후 2-4초간 표시

### 📐 기본 애니메이션 설정
```css
/* 초기 상태 */
.animated-element {
    opacity: 0;
    transform: translateY(30px); /* 또는 적절한 변형 */
    transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
}

/* 활성 상태 */
.animated-element.visible {
    opacity: 1;
    transform: translateY(0);
}
```

### ⚡ 호버 효과
```css
.hoverable {
    transition: transform 0.3s ease;
}

.hoverable:hover {
    transform: translateY(-5px); /* 카드 */
    /* 또는 */
    transform: scale(1.02); /* 이미지 */
}
```

---

## 슬라이드별 특화 사항

### 🏠 Slide1 (메인 페이지)
- **특징**: Back 버튼 없음
- **버튼**: "Start Presentation"
- **키보드**: 뒤로가기 키 무시
- **애니메이션**: 웅장한 로고 중심 애니메이션

### 📊 Slide2 (시장 기회)
- **특징**: 프로그레스 바 애니메이션
- **제외 요소**: `.metric-card`, `.country-item`, `.growth-card`
- **순서**: 타이틀 → 메트릭 → 차트 → 프로그레스바

### 🚧 Slide3 (3가지 장벽)
- **특징**: 클릭 가능한 데이터 항목
- **제외 요소**: `.barrier-card`, `.data-item`
- **순서**: 타이틀 → 카드들 순차 등장

### 📄 Slide4 (특허 혁신)
- **특징**: 특허 정보 중심
- **제외 요소**: `.innovation-card`, `.patent-image`
- **순서**: 특허 이미지 → 혁신 카드 → 제품 이미지

### 🏛️ Slide5 (FDA 승인)
- **특징**: FDA 프로세스 중심
- **제외 요소**: `.phase-card`, `.fda-image`
- **순서**: FDA 이미지 → Phase 카드 → Impact

### 🔬 Slide6 (기술 상세)
- **특징**: 기술 설명 중심
- **제외 요소**: `.benefit-card`, `.tech-image`
- **순서**: 이미지 → 라벨 → 혜택 카드

### 🎯 Slide7 (솔루션)
- **특징**: 문제해결 매트릭스
- **제외 요소**: `.barrier-card`, `.solution-card`
- **순서**: 문제 → 화살표 → 솔루션 → KiiS 로고

---

## 개발 가이드라인

### 🛠️ 필수 구현 체크리스트

#### 네비게이션
- [ ] `hover-zone` div 추가
- [ ] `navigation` div 추가 (visible 클래스용)
- [ ] 4가지 안전장치 JavaScript 구현
- [ ] 터치 디바이스 감지 및 분기 처리
- [ ] 키보드 이벤트 핸들러
- [ ] 첫 페이지 특수 처리 (Slide1)

#### 팝업 (필요시)
- [ ] `overlay` div 추가
- [ ] `source-popup` div 추가
- [ ] `sources` 객체 정의
- [ ] `showSource()`, `hideSource()` 함수

#### 애니메이션
- [ ] 로딩 시 요소별 초기 상태 설정
- [ ] 순차적 애니메이션 타이밍 구현
- [ ] 네비게이션 힌트 타이밍 (2-4초)

#### 반응형
- [ ] 모바일 CSS 미디어 쿼리
- [ ] 터치 이벤트 처리
- [ ] 네비게이션 크기 조정

### 🎯 코드 품질 기준

#### CSS
- 색상 변수 사용 (`#ffd700`, `#1e40af` 등)
- 일관된 네이밍 컨벤션
- 반응형 미디어 쿼리 포함

#### JavaScript
- 터치 디바이스 감지 분기
- 메모리 누수 방지 (clearTimeout)
- 콘솔 디버깅 메시지 (개발환경)

### 🚀 성능 최적화
- 이미지 오류 처리 (`onerror` 핸들러)
- 애니메이션 하드웨어 가속 (`transform` 사용)
- 이벤트 리스너 정리

---

## 체크리스트

### ✅ 새 슬라이드 생성 시

#### 기본 구조
- [ ] HTML5 DOCTYPE 및 meta 태그
- [ ] 공통 CSS 색상 체계 적용
- [ ] 반응형 컨테이너 구조

#### 네비게이션
- [ ] `hover-zone` 추가
- [ ] `navigation` 추가 (올바른 링크)
- [ ] JavaScript 네비게이션 시스템 복사
- [ ] 터치/PC 분기 처리 확인
- [ ] 키보드 네비게이션 테스트

#### 콘텐츠
- [ ] 슬라이드별 특화 제외 요소 설정
- [ ] 팝업 필요시 소스 데이터 정의
- [ ] 로딩 애니메이션 순서 결정

#### 테스트
- [ ] PC 호버 네비게이션 동작
- [ ] 모바일 스와이프/터치 동작  
- [ ] 키보드 단축키 동작
- [ ] 팝업 열기/닫기 동작
- [ ] 반응형 레이아웃 확인

### 🔍 QA 체크리스트

#### 브라우저 호환성
- [ ] Chrome (PC/Mobile)
- [ ] Safari (PC/Mobile)
- [ ] Firefox (PC)
- [ ] Edge (PC)

#### 디바이스 테스트
- [ ] 데스크톱 (1920x1080)
- [ ] 태블릿 (768x1024)
- [ ] 모바일 (375x667)

#### 접근성
- [ ] 키보드만으로 네비게이션 가능
- [ ] 터치 스크린에서 모든 기능 동작
- [ ] 시각적 피드백 제공

---

## 📝 버전 관리

### Git 브랜치 전략
```
main (배포용)
├── develop (개발용)
├── feature/slide-X (개별 슬라이드)
└── feature/design-system (디자인 시스템 업데이트)
```

### 커밋 메시지 규칙
```
feat: Add slide7 navigation system
fix: Mobile swipe navigation on slide3
docs: Update design system documentation
style: Improve hover animation timing
```

### 파일 구조
```
kiis-investor-pitch/
├── index.html (slide1)
├── slide2.html
├── slide3.html
├── ...
├── public/
│   └── images/
├── docs/
│   ├── DESIGN_SYSTEM.md (이 문서)
│   ├── DEVELOPMENT_GUIDE.md
│   └── CHANGELOG.md
└── README.md
```

---

## 🔄 업데이트 프로세스

1. **디자인 시스템 변경** → 모든 슬라이드에 일괄 적용
2. **새 슬라이드 추가** → 체크리스트 기반 구현
3. **버그 수정** → 해당 패턴의 모든 슬라이드 검토
4. **성능 개선** → 전체 시스템 벤치마크

---

*이 문서는 KiiS 프레젠테이션의 품질과 일관성을 보장하기 위한 살아있는 문서입니다. 새로운 요구사항이나 개선사항이 있을 때마다 업데이트됩니다.*
