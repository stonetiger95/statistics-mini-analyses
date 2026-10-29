# Statistics Mini Analyses

## 통계적 개념과 분석 방법을 적용한 소규모 사례 모음

통계학 복수전공 학사과정에서 수행한 분석 중 통계적 판단이 드러나는 사례를 선별해 다시 구성했습니다. 각 분석은 질문, 방법 선택, 결과, 진단과 한계를 한 흐름으로 기록하며 ARIMA, 다중검정, PCA·요인분석과 대응분석의 적용 경험을 보여줍니다.

| 분석 | 질문 | 방법 |
| --- | --- | --- |
| [Korea Zinc Time Series](analyses/korea-zinc-timeseries/) | 주가의 시계열 구조와 제한적인 단기 예측은 어떻게 확인할 수 있는가 | ARIMA |
| [Multiple Testing](analyses/multiple-testing-simulation/) | 반복 검정에서 거짓 양성은 어떻게 누적되며 보정은 무엇을 바꾸는가 | simulation, Bonferroni, BH-FDR |
| [Athletics Multivariate Analysis](analyses/athletics-multivariate/) | 여러 육상 기록의 공통 차원은 무엇인가 | PCA, Factor Analysis |
| [AIDS Correspondence Analysis](analyses/aids-correspondence-analysis/) | AZT 처치 시점과 AIDS 증상 범주의 상대적 연관 구조는 어떻게 나타나는가 | chi-square test, Correspondence Analysis |

## 저장소 사용

각 폴더의 `analysis.Rmd`는 분석 코드와 해석을, `analysis.html`은 렌더링된 결과를 담습니다. 데이터 재배포 조건이 분명하지 않은 두 분석은 원자료를 포함하지 않았으며, [데이터 안내](data/README.md)에 획득·배치 방법을 기록했습니다.

```r
renv::restore()
rmarkdown::render("analyses/multiple-testing-simulation/analysis.Rmd")
```

분석별 재현 가능 범위와 원본에서 변경한 표현은 [source notes](docs/source_notes.md)에 정리했습니다.

## 분석 및 해석 원칙

- 각 분석은 통계적 방법의 적용 과정과 해석을 보여주기 위한 탐색적 사례입니다.
- 관찰된 관계나 패턴을 인과관계로 확대하여 해석하지 않습니다.
- 데이터 출처, 분석 가정, 모형 진단 결과와 표본의 한계를 함께 제시합니다.

## License

코드와 문서는 [MIT License](LICENSE)로 배포합니다. 외부 데이터의 권리는 각 원 제공자에게 있으며, 이 저장소의 라이선스가 해당 데이터에 적용되지는 않습니다.
