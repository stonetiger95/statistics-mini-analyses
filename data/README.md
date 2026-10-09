# Data access

이 저장소는 출처와 재배포 조건이 확인된 범위에서만 데이터를 공개합니다.

## Korea Zinc 종가

- 출처: [KRX Data Marketplace](https://data.krx.co.kr/), 고려아연(010130, KOSPI) 개별종목 시세
- 분석 기간: 2024-01-02~2024-12-30(모형 적합), 2025-01-02~2025-01-08 중 첫 5거래일(제한적 비교)
- 공개 처리: KRX 홈페이지 이용약관은 사전 허락 없는 정보의 복제·배포를 제한하므로 CSV를 저장소에 포함하지 않습니다.
- 재현 방법: KRX에서 위 기간의 `일자`, `종가`를 CSV로 내려받아 각각 아래 경로에 둡니다.
  - `data/raw/korea-zinc-2024.csv`
  - `data/raw/korea-zinc-2025-first-5.csv`

원본 분석 파일의 첫 행은 CP949 한글 열 이름입니다. 분석 코드는 인코딩 차이를 피하기 위해 첫 행을 건너뛰고 두 열을 `date`, `price`로 지정합니다.

## Women’s national track records

- 자료 정의: 2005년 기준 54개 국가의 여자 국가기록, 7개 종목(100m, 200m, 400m, 800m, 1500m, 3000m, Marathon)
- 원 출처 표기: *IAAF/ATFS Track and Field Handbook for Helsinki 2005*, Ottavio Castellini 제공; Johnson & Wichern, *Applied Multivariate Statistical Analysis*의 예제 표로도 수록
- 공개 처리: 원자료의 재배포 허가를 확인하지 못해 저장소에 포함하지 않습니다.
- 재현 방법: 합법적으로 취득한 원자료를 `data/raw/trackrecord2005-women.txt`에 둡니다. 첫 행은 변수명, 첫 열은 국가 코드인 공백 구분 텍스트 형식입니다.

## Multiple-testing simulation

외부 데이터가 없습니다. `set.seed(12345)`로 모든 자료를 생성합니다.

## AIDS symptoms and AZT use

분석에 필요한 2×2 집계표(총 338명)는 `analysis.Rmd` 안에 명시했습니다. 자료 정의는 R의 `brglm2::aids` 문서와 Agresti(2002)에 공개되어 있으며 개인 수준 자료나 식별정보는 포함하지 않습니다.

`data/raw/`는 `.gitignore`로 제외됩니다. 외부 데이터의 라이선스와 이용약관은 이 저장소의 MIT License와 별개입니다.
