# KiiS 1차 데이터 소스 관리 시스템
**목적:** 신뢰할 수 있는 1차 소스 확보 및 관리  
**업데이트:** 2025년 7월 19일

---

## 🚨 **현재 문제 진단**

### **우리가 범한 근본적 오류**
```
문제 상황:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
❌ 1차 소스 없이 2차/3차 가공 데이터에 의존
❌ 출처 추적 없이 숫자만 사용
❌ 검증 없이 서로 다른 소스 혼용
❌ "신뢰할 만하다"는 가정하에 분석 진행

결과: 120M vs 178M vs 1.78M 혼란
```

### **진짜 필요한 것**
- ✅ **직접 접근 가능한 1차 소스**
- ✅ **소스별 신뢰도 등급 시스템**
- ✅ **정기 업데이트 가능한 데이터**
- ✅ **검증 프로세스 표준화**

---

## 📋 **1차 소스 확보 액션 플랜**

### **Phase 1: 즉시 확보해야 할 1차 소스 (이번 주)**

#### **1) American Academy of Implant Dentistry (AAID)**
- **목표**: PDF에서 인용한 "120M" 원본 확인
- **액션**: AAID 공식 웹사이트에서 최신 통계 다운로드
- **담당**: Claude web search + CEO 검토
- **기한**: 7/20 일요일

#### **2) American Dental Association (ADA)**
- **목표**: 미국 임플란트 시장 공식 통계
- **액션**: ADA Health Policy Institute 데이터 확보
- **링크**: ada.org → Research → Health Policy Institute
- **기한**: 7/21 월요일

#### **3) Bureau of Labor Statistics (BLS)**
- **목표**: 치과의사 수, 지역별 분포
- **액션**: BLS Occupational Employment Statistics 확보
- **기한**: 7/21 월요일

### **Phase 2: 업계 1차 소스 확보 (다음 주)**

#### **4) FDA Medical Device Database**
- **목표**: 임플란트 승인 현황, 시장 데이터
- **액션**: FDA 510(k) 데이터베이스 검색

#### **5) 주요 임플란트 업체 공개 자료**
- **Straumann**: Annual Report, Investor Relations
- **Nobel Biocare**: Market Research Publications  
- **Dentsply Sirona**: Industry Reports

#### **6) 학술 논문 데이터**
- **PubMed**: 최근 5년 임플란트 시장 연구
- **Journal of Dental Research**: 시장 동향 논문

## 📁 **GitHub 1차 소스 관리 시스템**

### **폴더 구조**
```
📁 kiis-investor-pitch/
├── 📁 docs/
│   ├── 📄 KIIS_Project_Master.md
│   ├── 📁 data-sources/                    ← 새로 생성
│   │   ├── 📁 primary-sources/
│   │   │   ├── 📄 DATA_REGISTRY.md         ← 1차 소스 레지스트리
│   │   │   ├── 📄 ACP_Statistics.md        ← ACP 공식 데이터
│   │   │   ├── 📄 AAID_Statistics.md       ← AAID 공식 데이터  
│   │   │   ├── 📄 ADA_MarketData.md        ← ADA 시장 데이터
│   │   │   ├── 📄 FDA_DeviceData.md        ← FDA 의료기기 데이터
│   │   │   └── 📄 Academic_Papers.md       ← 학술 논문 모음
│   │   ├── 📁 verification-logs/
│   │   │   ├── 📄 2025-07-19_Verification.md ← 오늘 검증 로그
│   │   │   └── 📄 Monthly_Updates.md        ← 월간 업데이트 로그
│   │   └── 📁 conflicting-sources/
│   │       └── 📄 Discrepancy_Analysis.md   ← 상충 데이터 분석
│   ├── 📄 Dentist_Interview_Results.md
│   └── 📄 Financial_Model_Updates.md
```

### **핵심 파일 역할**

#### **📄 DATA_REGISTRY.md**
**목적:** 모든 1차 소스의 마스터 인덱스
```markdown
# KiiS 1차 데이터 소스 레지스트리

## 검증 완료 데이터 (Tier 1)
| 지표 | 수치 | 출처 | 업데이트 | 신뢰도 | 파일 |
|------|------|------|----------|--------|------|
| 미국 치아상실자 | 178M | ACP | 2024 | AAA+ | ACP_Statistics.md |
| 임플란트 보유자 | 3M | AAID | 2025 | AAA+ | AAID_Statistics.md |
| 보급률 증가 | 0.7%→5.7% | Harvard/PMC | 2018 | AA+ | Academic_Papers.md |

## 검증 필요 데이터 (Tier 2)
| 지표 | 수치 | 출처 | 상태 | 액션 |
|------|------|------|------|------|
| 연간 시술 건수 | 1.5M/년 | PDF 인용 | 1차 소스 확인 필요 | AAID 직접 확인 |
```

#### **📄 ACP_Statistics.md**
**목적:** American College of Prosthodontists 공식 데이터 관리
```markdown
# ACP (American College of Prosthodontists) 공식 통계

## 핵심 데이터
- **치아상실자**: 178 million Americans missing at least one tooth
- **완전 무치악**: 40 million Americans missing all teeth
- **출처**: gotoapro.org/facts-figures/
- **최종 확인**: 2025-07-19
- **신뢰도**: AAA+ (공식 기관)

## 원문 인용
"The American College of Prosthodontists (ACP) found that 178 million people 
in the United States are missing at least one tooth. The ACP also found that 
40 million Americans are missing all of their top and bottom rows of teeth."

## 검증 내역
- ✅ 2025-07-19: 웹 검색으로 재확인
- ✅ 다중 소스에서 동일 수치 확인
- ✅ 공식 웹사이트 직접 확인
```

### **관리 워크플로우**

#### **일일 데이터 체크**
```bash
# 매일 아침 루틴
1. DATA_REGISTRY.md 확인
2. 사용할 데이터의 최신성 점검
3. 새로운 데이터 발견 시 즉시 기록
4. 상충 데이터 발견 시 Discrepancy_Analysis.md에 기록
```

#### **주간 검증 프로세스**
```bash
# 매주 금요일 루틴
1. 모든 Tier 1 데이터 재검증
2. Tier 2 데이터 → Tier 1 승격 검토
3. 오래된 데이터 업데이트 확인
4. Monthly_Updates.md 갱신
```

#### **신규 데이터 추가 프로세스**
```bash
# 새로운 데이터 발견 시
1. 출처 신뢰도 평가 (AAA+ ~ C)
2. 기존 데이터와 교차 검증
3. 해당 파일에 원문 + 검증 내역 기록
4. DATA_REGISTRY.md 업데이트
5. CEO 보고 (중요 데이터의 경우)
```
