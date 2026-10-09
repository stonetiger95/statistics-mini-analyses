# Source notes

## 선별 원칙

통계학 복수전공 학사과정에서 작성한 자료 중 코드, 데이터 정의, 해석 또는 렌더링 결과가 실제로 남아 있는 항목만 검토했습니다. 공개본에서는 과제 번호와 제출용 문구를 제거하고 분석 문제 중심으로 다시 서술했습니다. 수치가 불리하거나 진단이 실패한 부분도 삭제하지 않았습니다.

## 분석별 원본 근거

### Korea Zinc time series

- 원본에는 2024~2025년 자료로 정상성을 살핀 초기 문서와, 2024년 244거래일에 ARIMA(0,1,0)을 적합하고 2025년 첫 5거래일과 비교한 문서가 있습니다.
- 초기 문서는 시장 휴일을 전일 종가로 채운 뒤 `frequency = 365`를 사용했습니다. 이는 동일값 반복으로 인위적 자기상관을 만들 수 있어 공개본 분석에서는 사용하지 않고, 거래일 순서를 시간 인덱스로 사용했습니다.
- 원본의 최종 모형은 잔차 자기상관을 남겼습니다. 따라서 공개본은 결과를 **baseline forecast**로 제한해 표현합니다.

### Multiple-testing simulation

- 원본은 10,000개 가설, 1,000회 반복, 비귀무 비율 0.1, 효과 평균 2의 합성 실험을 사용했습니다.
- unadjusted, Bonferroni, BH 방법이 모두 원본 코드에 존재합니다.
- 공개본은 같은 seed와 생성 가정을 유지하되, 메모리 사용을 줄이기 위해 반복별로 자료를 생성합니다. 비교 지표를 기각 수, 거짓 양성 수, FWER, FDP, power로 명확히 정리했습니다.

### Athletics multivariate analysis

- 동일 자료에 대한 PCA 문서와 PCFA/MLFA 문서가 각각 존재합니다.
- 공개본은 두 문서를 하나의 질문으로 연결하고, 국가 순위나 선수 능력 평가보다 변수 구조와 방법 간 차이에 집중합니다.
- 원본의 2요인 선택은 scree plot과 누적 설명력에 주로 의존하므로, 별도 검증이 제한적이라는 점을 남겼습니다.

### AIDS correspondence analysis

- 원본에는 338명의 race, AZT use, AIDS symptoms로 구성한 Burt matrix와 AZT×symptoms 2×2 표의 대응분석 코드가 있습니다.
- 공개본은 정의가 가장 명확한 2×2 표를 중심으로 재구성했습니다. 2×2 대응분석은 비자명 차원이 하나뿐이므로 1차원 구조로 표현합니다.
- 자료 정의는 [CRAN `brglm2::aids` documentation](https://search.r-project.org/CRAN/refmans/brglm2/html/aids.html)에 근거해 보완했습니다. 이 문서는 Agresti(2002)와 1991년 2월 15일자 *New York Times*를 출처로 제시합니다.

## 데이터 공개 판단

- KRX Data Marketplace의 [홈페이지 이용약관](https://data.krx.co.kr/contents/MMC/COMS/client/MMCCOMS002_S1.cmd?type=C)은 거래소의 사전 허락 없는 정보 복제·배포·전송을 제한합니다. 따라서 주가 CSV는 제외했습니다.
- 육상 원자료는 출처는 식별했지만 공개 저장소 재배포 허가를 확인하지 못했습니다. 원자료는 제외하고 정의와 취득 단서만 제공합니다.
- 합성 자료는 코드로 생성하며, AIDS 자료는 공개 문헌의 소규모 집계표만 코드에 명시합니다.

## 제외 후보

- Salmon LDA: 원본 코드와 `salmon.txt`는 존재하지만, 우선순위 4개가 서로 다른 통계적 판단을 충분히 보여주므로 이번 저장소에서는 제외했습니다.
- 단순 AR/MA simulation, protein 기초 EDA, 기초 문법 자료, orphan Excel/Spotify 파일, wine classification은 선별 목적과 검증 수준에 맞지 않아 포함하지 않았습니다.
