# KiiS 투자자 프레젠테이션 디자인 시스템 v2.0

## 📋 목차
1. [핵심 철학](#핵심-철학)
2. [투자자 프레젠테이션 원칙](#투자자-프레젠테이션-원칙)
3. [모바일 최적화 전략](#모바일-최적화-전략)
4. [타이포그래피 시스템](#타이포그래피-시스템)
5. [레이아웃 및 간격 체계](#레이아웃-및-간격-체계)
6. [색상 및 시각적 위계](#색상-및-시각적-위계)
7. [네비게이션 시스템](#네비게이션-시스템)
8. [애니메이션 및 상호작용](#애니메이션-및-상호작용)
9. [개발 구현 가이드](#개발-구현-가이드)
10. [품질 보증 체크리스트](#품질-보증-체크리스트)

---

## 핵심 철학

### 🎯 내용적 가치
- **사업에 대한 내적 확신**: 데이터와 논리로 뒷받침되는 확고한 비전 제시
- **환자를 위한 진정성**: 178M 환자의 절실함을 진정성 있게 전달
- **혁신의 당위성**: 기술적 우월성과 시장 기회의 완벽한 조합

### 🎨 형식적 원칙
- **가독성 우선**: 모든 화면 크기에서 즉시 이해 가능한 정보 전달
- **간결성**: 핵심 메시지에 집중, 불필요한 요소 제거
- **직관적 흐름**: 논리적이고 자연스러운 정보 구조
- **전문성**: 투자자들이 신뢰할 수 있는 완성도

---

## 투자자 프레젠테이션 원칙

### 💼 성공적인 투자 피치의 핵심 요소

#### 1. **즉시 이해 가능한 가치 제안**
- 첫 3초 내 핵심 메시지 전달
- 시각적 임팩트와 명확한 텍스트의 조화
- 감정적 공감과 논리적 설득의 균형

#### 2. **데이터 중심의 신뢰성**
- 구체적 숫자와 통계 활용
- 출처가 명확한 시장 데이터
- 클릭 가능한 참조 자료로 투명성 확보

#### 3. **문제-해결의 명확한 구조**
- 환자의 절실함 → KiiS의 솔루션 → 시장 기회
- 감정적 몰입 → 기술적 확신 → 비즈니스 잠재력

### 📊 벤치마크 분석 결과
- **Y Combinator Demo Day**: 간결한 메시지, 대담한 타이포그래피
- **Sequoia Capital Deck**: 데이터 시각화, 논리적 흐름
- **Andreessen Horowitz Portfolio**: 모바일 퍼스트, 인터랙티브 요소

---

## 모바일 최적화 전략

### 📱 다단계 반응형 시스템

#### **Viewport 설정 (필수)**
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
```

#### **브레이크포인트 전략**
```css
/* 데스크톱 우선 설계 */
@media (max-width: 1200px) { /* 태블릿 */ }
@media (max-width: 768px)  { /* 중간 모바일 */ }
@media (max-width: 480px)  { /* 갤럭시 S 시리즈 */ }
@media (max-width: 360px)  { /* 컴팩트 폰 */ }
```

### 🎯 갤럭시 스마트폰 최적화 원칙

#### **1. 텍스트 가독성 보장**
- 최소 12px 폰트 크기 유지
- 충분한 줄 간격 (line-height: 1.3-1.4)
- 고대비 색상 조합

#### **2. 터치 친화적 인터페이스**
- 최소 44px 터치 영역
- 충분한 요소 간 간격
- 스와이프 제스처 지원

#### **3. 세로 우선 레이아웃**
- 카드 중심의 수직 스택
- 가로 스크롤 최소화
- 중앙 정렬 우선

---

## 타이포그래피 시스템

### 📝 폰트 크기 위계 (slide2 성공 원칙 기반)

#### **데스크톱 기준**
```css
/* 메인 타이틀 */
.hero-title { 
    font-size: 48px; 
    line-height: 1.1; 
    font-weight: bold; 
}

/* 섹션 제목 */
.section-title { 
    font-size: 28-32px; 
    line-height: 1.2; 
    font-weight: bold; 
}

/* 카드 제목 */
.card-title { 
    font-size: 20-24px; 
    line-height: 1.2; 
    font-weight: 600; 
}

/* 서브 제목 */
.subtitle { 
    font-size: 18-26px; 
    line-height: 1.3; 
    font-weight: 600; 
}

/* 본문 텍스트 */
.body-text { 
    font-size: 16-18px; 
    line-height: 1.4; 
    font-weight: 400; 
}

/* 작은 텍스트 */
.small-text { 
    font-size: 14-16px; 
    line-height: 1.3; 
    font-weight: 400; 
}
```

#### **모바일 최적화 비율**
```css
/* 768px 이하 */
.hero-title { font-size: 28-36px; }    /* 원본의 75% */
.section-title { font-size: 20-24px; } /* 원본의 75% */
.card-title { font-size: 16-18px; }    /* 원본의 80% */
.subtitle { font-size: 14-22px; }      /* 원본의 80% */
.body-text { font-size: 14-16px; }     /* 원본의 85% */

/* 480px 이하 (갤럭시 S 표준) */
.hero-title { font-size: 24-28px; }    /* 원본의 60% */
.section-title { font-size: 18-20px; } /* 원본의 65% */
.card-title { font-size: 15-16px; }    /* 원본의 70% */
.subtitle { font-size: 13-16px; }      /* 원본의 70% */
.body-text { font-size: 13-14px; }     /* 원본의 80% */

/* 360px 이하 (컴팩트) */
.hero-title { font-size: 22-24px; }    /* 원본의 50% */
.section-title { font-size: 16-18px; } /* 원본의 55% */
.card-title { font-size: 14-15px; }    /* 원본의 65% */
.subtitle { font-size: 12-14px; }      /* 원본의 65% */
.body-text { font-size: 12-13px; }     /* 원본의 75% */
```

### 🎨 폰트 스타일링 원칙

#### **위계 구조**
1. **Hero Level**: 임팩트, 감정적 어필
2. **Section Level**: 논리적 구분, 명확한 주제
3. **Card Level**: 구체적 정보, 실행 가능한 내용
4. **Detail Level**: 보조 설명, 세부 데이터

#### **가독성 최적화**
```css
/* 필수 속성 */
font-family: 'Arial', 'Helvetica', sans-serif;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
text-rendering: optimizeLegibility;

/* 줄 간격 */
line-height: 1.1; /* 타이틀 */
line-height: 1.2; /* 제목 */
line-height: 1.3; /* 카드 콘텐츠 */
line-height: 1.4; /* 본문 */
```

---

## 레이아웃 및 간격 체계

### 📐 그리드 시스템

#### **컨테이너 구조**
```css
.container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 40px 60px; /* 데스크톱 */
}

/* 모바일 패딩 조정 */
@media (max-width: 768px) {
    .container { padding: 20px 15px; }
}

@media (max-width: 480px) {
    .container { padding: 15px 10px; }
}

@media (max-width: 360px) {
    .container { padding: 12px 8px; }
}
```

#### **카드 간격 시스템**
```css
/* 데스크톱 */
.card-grid { gap: 40px 60px; }
.card-margin { margin-bottom: 20px; }

/* 태블릿 */
@media (max-width: 768px) {
    .card-grid { gap: 30px; }
    .card-margin { margin-bottom: 15px; }
}

/* 모바일 */
@media (max-width: 480px) {
    .card-grid { gap: 20px; }
    .card-margin { margin-bottom: 12px; }
}
```

### 🎯 정렬 원칙

#### **데스크톱**: 기능적 정렬
- 읽기 흐름을 고려한 왼쪽 정렬
- 데이터는 중앙 또는 오른쪽 정렬
- 카드 헤더는 좌측 정렬

#### **모바일**: 중앙 정렬 우선
```css
@media (max-width: 768px) {
    .card-content { text-align: center; }
    .card-header { justify-content: center; }
    .data-display { text-align: center; }
}
```

---

## 색상 및 시각적 위계

### 🎨 색상 시스템 (slide2 검증 완료)

#### **Primary Colors**
```css
:root {
    /* 배경 그라디언트 */
    --bg-gradient: radial-gradient(ellipse at center, #1e40af 0%, #0f172a 70%, #000000 100%);
    
    /* 브랜드 색상 */
    --brand-gold: #ffd700;
    --brand-blue: #1e40af;
    --brand-blue-dark: #1d4ed8;
    
    /* 기능 색상 */
    --success: #10b981;
    --warning: #f59e0b;
    --danger: #ef4444;
    --info: #3b82f6;
    
    /* 텍스트 색상 */
    --text-primary: #ffffff;
    --text-secondary: #e0e7ff;
    --text-accent: #ffd700;
    --text-muted: #94a3b8;
}
```

#### **카드 색상 체계**
```css
/* 문제/위기 카드 */
.crisis-card {
    background: rgba(55, 65, 81, 0.8);
    border-color: #374151;
}

/* 솔루션 카드 */
.solution-card {
    background: rgba(30, 64, 175, 0.3);
    border-color: #1e40af;
}

/* 성공/희망 카드 */
.success-card {
    background: linear-gradient(135deg, #059669, #10b981);
    color: #ffffff;
}

/* 데이터 카드 */
.data-card {
    background: rgba(255, 255, 255, 0.05);
    border-color: #ffd700;
}
```

### 🔍 시각적 위계 원칙

#### **Z-Index 관리**
```css
/* 레이어 구조 */
.navigation { z-index: 1000; }
.popup-overlay { z-index: 1500; }
.popup-content { z-index: 1600; }
.tooltip { z-index: 2000; }
```

#### **투명도 체계**
```css
/* 배경 투명도 */
.card-background { background: rgba(0, 0, 0, 0.4); }
.overlay { background: rgba(0, 0, 0, 0.8); }
.hover-effect { background: rgba(255, 215, 0, 0.1); }
```

---

## 네비게이션 시스템

### 🧭 통합 네비게이션 (slide2 성공 모델)

#### **구조**
```html
<!-- 호버 감지 영역 -->
<div class="hover-zone" id="hoverZone"></div>

<!-- 네비게이션 바 -->
<div class="navigation" id="navigation">
    <a href="[prev].html" class="nav-btn prev">Back</a>
    <a href="[next].html" class="nav-btn next">Next</a>
</div>
```

#### **스타일링**
```css
.navigation {
    position: fixed;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    background: rgba(0, 0, 0, 0.9);
    border: 2px solid rgba(255, 215, 0, 0.3);
    border-radius: 50px;
    backdrop-filter: blur(15px);
    opacity: 0;
    visibility: hidden;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.navigation.visible {
    opacity: 1;
    visibility: visible;
}
```

### 📱 멀티 디바이스 상호작용

#### **PC (마우스)**
- 하단 120px 영역 호버시 표시
- 네비게이션 호버시 유지
- 마우스 벗어나면 1.5초 후 숨김

#### **모바일 (터치)**
- 하단 터치로 표시/숨김
- 좌우 스와이프로 페이지 이동
- 빈 영역 탭으로 토글

#### **키보드**
- `←/↑`: 이전 페이지
- `→/↓/Space`: 다음 페이지
- `N`: 네비게이션 토글
- `ESC`: 팝업 닫기

---

## 애니메이션 및 상호작용

### 🎬 로딩 애니메이션 원칙

#### **순차적 등장 시퀀스**
```javascript
// 로딩 순서 (slide2 최적화 모델)
1. 헤더 (0ms)
2. 메인 콘텐츠 (400ms)
3. 카드들 순차 (600ms, 200ms 간격)
4. 하단 섹션 (1200ms)
5. 네비게이션 힌트 (2000ms, 2초간 표시)
```

#### **기본 애니메이션 설정**
```css
/* 초기 상태 */
.animate-in {
    opacity: 0;
    transform: translateY(30px);
    transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
}

/* 활성 상태 */
.animate-in.visible {
    opacity: 1;
    transform: translateY(0);
}

/* 카드별 차별화 */
.slide-left { transform: translateX(-20px); }
.slide-right { transform: translateX(20px); }
.scale-in { transform: scale(0.95); }
```

### ⚡ 호버 및 클릭 효과

#### **카드 호버**
```css
.card {
    transition: all 0.3s ease;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
}
```

#### **클릭 가능한 요소**
```css
.clickable {
    cursor: pointer;
    position: relative;
    transition: all 0.3s ease;
}

.clickable::after {
    content: "ℹ️";
    position: absolute;
    opacity: 0.6;
    transition: opacity 0.3s ease;
}

.clickable:hover::after {
    opacity: 1;
}
```

---

## 개발 구현 가이드

### 🛠️ 필수 HTML 구조

#### **기본 템플릿**
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>KiiS - [슬라이드 제목]</title>
    <!-- 스타일 -->
</head>
<body>
    <div class="container">
        <!-- 메인 헤더 -->
        <div class="main-header">
            <h1 class="title">[제목]</h1>
            <p class="subtitle">[부제목]</p>
        </div>
        
        <!-- 메인 콘텐츠 -->
        <div class="main-content">
            <!-- 콘텐츠 영역 -->
        </div>
    </div>
    
    <!-- 팝업 시스템 (필요시) -->
    <div class="source-overlay" id="sourceOverlay"></div>
    <div class="source-popup" id="sourcePopup">
        <button class="source-close" id="sourceCloseBtn">&times;</button>
        <div class="source-title" id="sourceTitle"></div>
        <div class="source-content" id="sourceContent"></div>
    </div>
    
    <!-- 네비게이션 -->
    <div class="hover-zone" id="hoverZone"></div>
    <div class="navigation" id="navigation">
        <a href="[prev].html" class="nav-btn prev">Back</a>
        <a href="[next].html" class="nav-btn next">Next</a>
    </div>
    
    <!-- JavaScript -->
</body>
</html>
```

### 📱 반응형 CSS 템플릿

#### **기본 구조**
```css
/* 기본 스타일 (데스크톱) */
.element {
    /* 데스크톱 스타일 */
}

/* 태블릿 */
@media (max-width: 1200px) {
    .element {
        /* 태블릿 조정 */
    }
}

/* 중간 모바일 */
@media (max-width: 768px) {
    .element {
        font-size: calc(원본크기 * 0.75);
        padding: calc(원본패딩 * 0.8);
        text-align: center;
    }
}

/* 갤럭시 S 표준 */
@media (max-width: 480px) {
    .element {
        font-size: calc(원본크기 * 0.6);
        padding: calc(원본패딩 * 0.6);
        margin-bottom: calc(원본마진 * 0.8);
    }
}

/* 컴팩트 폰 */
@media (max-width: 360px) {
    .element {
        font-size: calc(원본크기 * 0.5);
        padding: calc(원본패딩 * 0.5);
    }
}
```

### 🎯 JavaScript 핵심 패턴

#### **네비게이션 시스템**
```javascript
// 전역 변수
let isNavigationVisible = false;
let hideTimeout;
const isTouchDevice = 'ontouchstart' in window || navigator.maxTouchPoints > 0;

// 네비게이션 표시/숨김
function showNavigation() {
    if (hideTimeout) clearTimeout(hideTimeout);
    document.getElementById('navigation').classList.add('visible');
    isNavigationVisible = true;
}

function hideNavigation(delay = 2000) {
    hideTimeout = setTimeout(() => {
        document.getElementById('navigation').classList.remove('visible');
        isNavigationVisible = false;
    }, delay);
}

// 디바이스별 이벤트 처리
if (!isTouchDevice) {
    // PC: 마우스 이벤트
    document.addEventListener('mousemove', handleMouseMove);
} else {
    // 모바일: 터치 이벤트
    document.addEventListener('touchstart', handleTouchStart);
    document.addEventListener('touchend', handleTouchEnd);
}

// 키보드 네비게이션
document.addEventListener('keydown', handleKeydown);
```

#### **팝업 시스템**
```javascript
// 팝업 표시
function showSource(sourceId) {
    const source = sources[sourceId];
    if (!source) return;
    
    document.getElementById('sourceTitle').textContent = source.title;
    document.getElementById('sourceContent').innerHTML = source.content;
    
    document.getElementById('sourceOverlay').style.display = 'block';
    document.getElementById('sourcePopup').style.display = 'block';
    
    // 스크롤 방지
    document.body.dataset.originalOverflow = document.body.style.overflow || 'auto';
    document.body.style.overflow = 'hidden';
}

// 팝업 숨김
function hideSource() {
    document.getElementById('sourceOverlay').style.display = 'none';
    document.getElementById('sourcePopup').style.display = 'none';
    
    // 스크롤 복원
    const originalOverflow = document.body.dataset.originalOverflow || 'auto';
    document.body.style.overflow = originalOverflow;
    delete document.body.dataset.originalOverflow;
}
```

---

## 품질 보증 체크리스트

### ✅ 개발 완료 체크리스트

#### **기본 구조**
- [ ] HTML5 DOCTYPE 및 올바른 meta 태그
- [ ] Viewport 설정 포함
- [ ] 시맨틱 HTML 구조 사용
- [ ] 접근성 속성 (alt, aria-label 등)

#### **타이포그래피**
- [ ] 모든 텍스트 크기가 가이드라인 준수
- [ ] 모바일에서 최소 12px 유지
- [ ] 적절한 줄 간격 설정
- [ ] 폰트 로딩 최적화

#### **레이아웃**
- [ ] 반응형 그리드 정상 동작
- [ ] 모바일에서 중앙 정렬 적용
- [ ] 적절한 간격 및 패딩
- [ ] 터치 영역 44px 이상

#### **상호작용**
- [ ] 네비게이션 4가지 방식 모두 동작
- [ ] 팝업 열기/닫기 정상 동작
- [ ] 스크롤 잠금/해제 정상 동작
- [ ] 키보드 네비게이션 지원

#### **성능**
- [ ] 초기 로딩 3초 이내
- [ ] 애니메이션 60fps 유지
- [ ] 이미지 최적화 완료
- [ ] JavaScript 오류 없음

### 🔍 디바이스별 테스트

#### **필수 테스트 환경**
- [ ] **Chrome Desktop** (1920x1080)
- [ ] **Chrome Mobile** (Galaxy S 시리즈)
- [ ] **Safari Desktop** (MacBook)
- [ ] **Safari Mobile** (iPhone)
- [ ] **Firefox Desktop**
- [ ] **Edge Desktop**

#### **상호작용 테스트**
- [ ] **마우스 호버** 네비게이션
- [ ] **터치** 제스처 (탭, 스와이프)
- [ ] **키보드** 단축키
- [ ] **팝업** 모든 방식으로 열기/닫기

### 📊 성능 기준

#### **로딩 성능**
- 초기 렌더링: < 1초
- 완전 로딩: < 3초
- 애니메이션 시작: < 1.5초

#### **사용성 기준**
- 터치 반응: < 100ms
- 네비게이션 표시: < 200ms
- 페이지 전환: < 500ms

### 🎯 투자자 프레젠테이션 품질 기준

#### **콘텐츠 품질**
- [ ] 핵심 메시지 3초 내 전달
- [ ] 데이터 출처 명확히 표시
- [ ] 논리적 정보 흐름 구성
- [ ] 감정적 임팩트와 논리적 설득 균형

#### **시각적 완성도**
- [ ] 모든 요소의 정렬 일관성
- [ ] 색상 대비 4.5:1 이상 유지
- [ ] 타이포그래피 위계 명확
- [ ] 브랜드 아이덴티티 일관성

#### **기술적 신뢰성**
- [ ] 모든 링크 및 상호작용 동작
- [ ] 크로스 브라우저 호환성
- [ ] 모바일 최적화 완성도
- [ ] 오류 없는 코드 품질

---

## 버전 관리 및 업데이트

### 📝 문서 버전 히스토리
- **v1.0**: 초기 디자인 시스템 구축
- **v2.0**: slide2 모바일 최적화 성공 사례 반영
  - 투자자 프레젠테이션 원칙 추가
  - 갤럭시 스마트폰 최적화 전략 수립
  - 타이포그래피 시스템 정교화
  - 품질 보증 프로세스 강화

### 🔄 지속적 개선 프로세스
1. **실제 사용 피드백** 수집
2. **성능 모니터링** 데이터 분석
3. **최신 웹 표준** 적용
4. **투자자 반응** 기반 조정

---

*이 디자인 시스템은 KiiS의 투자자 프레젠테이션 품질을 보장하고, 환자를 위한 우리의 진정성과 사업에 대한 확신을 효과적으로 전달하기 위한 살아있는 문서입니다.*
