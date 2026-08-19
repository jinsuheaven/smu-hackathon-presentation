# SMU Hackathon 발표용 분석 코드

숙명여대 Snowflake 해커톤 발표를 위해 실행 결과가 포함된 분석 Notebook과 인수인계 문서를 모아둔 저장소입니다.

## 대표 Notebook

- [`notebooks/presentation_final_analysis_executed.ipynb`](notebooks/presentation_final_analysis_executed.ipynb): 전력수요·송전 인프라·건강부담·제조공정 수요관리 결과를 한 흐름으로 정리한 발표용 통합 Notebook

## 보조 분석 Notebook

- `power_facility_overview_presentation_final_review_20260819_executed.ipynb`: 전국 전력시설 공간 분포
- `sido_area_adjusted_demand_infrastructure_v5_final_review_20260819_executed.ipynb`: 시도별 면적보정 수요·송전 인프라 불균형
- `regional_health_burden_analysis_v2_final_review_20260819_executed.ipynb`: 시도별 건강부담 보조 분석
- `manufacturing_ai_peak_team_clean_export_final_2021_executed.ipynb`: 제조공정 전력예측 및 생산시간 분산 시뮬레이션

## 발표용 그림

`figures/`에는 발표자료에서 실제로 사용한 핵심 결과 그림을 모아 두었다. 그림은 실행 결과를 빠르게 확인하기 위한 보조 자료이며, 수치의 근거와 분석 흐름은 각 실행 Notebook을 기준으로 한다.

| 파일 | 내용 | 연결 Notebook |
|---|---|---|
| `01_nationwide_power_facilities_map.jpeg` | 전국 송전탑·송전선로·변전소 분포 | 전력시설 현황 Notebook |
| `02_sido_demand_index.png` | 시도별 수요지수 | 면적보정 수요·인프라 Notebook |
| `03_manufacturing_model_performance.png` | 제조공정 전력예측 성능(팀 합의 R²=0.8995) | 제조공정 Notebook |
| `04_production_shift_official_40pct.png` | 생산량 유지, 40% 생산시간 분산 시 평균 피크 1.06% 감소 | 제조공정 Notebook |
| `05_region_process_overlap.png` | 지역 전력피크와 제조공정 고부하 시간 중첩률(전남 80%) | 제조공정 Notebook |
| `06_demand_variable_correlation_heatmap.png` | 전력수요 후보 변수 상관관계 | 통합 Notebook 보조 결과 |
| `07_health_burden_correlation_nonsignificant.png` | 건강부담 상관분석 보조 결과(r=0.419714, p=0.093503, n=17) | 건강부담 Notebook |

발표 수치가 일관되도록 중간 산출물과 수치가 다른 시나리오 그림은 공개 그림 목록에서 제외했다. 원본 데이터, 개인 경로, 인증정보는 저장소에 포함하지 않는다.

## 주요 결과

- 상대적 송전망 부담 가능성 상위 지역: 전라남도·경상북도·충청남도
- 건강부담 분석: 시도 단위 통계적 유의성이 확인되지 않아 보조 결과로 해석
- 제조공정 시뮬레이션: 생산량을 유지하면서 40% 생산시간 분산 시 평균 피크전력 약 1.06% 감소
- 전남: 지역 전력 고부하 시간과 제조공정 고부하 시간의 중첩률 80%

## 해석상 주의

이 분석은 설비용량·선로 부하율·실제 특정 업체의 감축량을 직접 측정한 것이 아닙니다. 결과는 지역별 상대적 부담 가능성과 수요관리 적용 가능성을 탐색한 결과이며, 송전망 부족이나 인과관계로 해석하지 않습니다.

이 저장소에는 재현에 필요한 원본 데이터가 포함되어 있지 않으며, 실행 결과와 코드 확인을 위한 발표용 패키지입니다.
