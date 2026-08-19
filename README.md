# SMU Hackathon | 심사위원용 발표 코드

숙명여대 Snowflake Summer Camp 해커톤의 발표용 코드와 실행 결과를 정리한 저장소입니다.

## 프로젝트 한 줄 요약

전력수요가 높은 지역과 송전 인프라 부담이 집중된 지역의 공간적 차이를 확인하고, 지역사회 건강부담과 제조공정 수요관리 가능성을 함께 탐색했습니다.

> **빠른 확인 순서:** `figures/`의 발표용 그림 → 발표용 통합 Notebook → 세부 분석 Notebook

## 핵심 결과

1. 면적보정 수요·인프라 비교에서 전라남도·경상북도·충청남도가 상대적 송전망 부담 가능성 상위 지역으로 나타났습니다.
2. 건강부담 분석은 시도 단위에서 통계적으로 유의한 관계가 확인되지 않아 보조 결과로 해석했습니다 (Pearson r=0.419714, p=0.093503, n=17).
3. 공개 제조공정 데이터 기반 시뮬레이션에서 생산량을 유지한 채 40%의 생산시간을 분산했을 때 평균 피크전력이 137.47에서 135.40으로 감소했습니다 (약 1.06%).
4. 전남은 지역 전력 고부하 시간과 제조공정 고부하 시간의 중첩률이 80%로 나타나 수요관리 우선 적용 사례로 제안했습니다.

## 분석 흐름

전력시설 공간 분포 확인 → 시도별 수요·면적보정 송전 인프라 비교 → 건강부담 보조 분석 → 제조공정 전력예측 → 생산시간 분산 시뮬레이션 → 지역 적용 가능성 제안

## 심사위원이 먼저 볼 파일

### 1. 발표용 통합 Notebook

[`notebooks/presentation_final_analysis_executed.ipynb`](notebooks/presentation_final_analysis_executed.ipynb)

전력시설 현황, 수요·송전 인프라 불균형, 건강부담 보조 분석, 제조공정 수요관리 결과를 한 흐름으로 정리한 대표 파일입니다. 실행 결과가 포함되어 있어 코드와 결과를 함께 확인할 수 있습니다.

### 2. 발표용 정적 그림

GitHub나 VS Code에서 Notebook의 Plotly 지도가 렌더링되지 않는 경우에도 아래 그림을 열면 발표 결과를 바로 확인할 수 있습니다.

| 그림 | 내용 |
|---|---|
| [`01_nationwide_power_facilities_map.jpeg`](figures/01_nationwide_power_facilities_map.jpeg) | 전국 송전탑·송전선로·변전소 분포 |
| [`02_sido_demand_index.png`](figures/02_sido_demand_index.png) | 시도별 전력수요 지수 |
| [`03_manufacturing_model_performance.png`](figures/03_manufacturing_model_performance.png) | 제조공정 전력예측 성능 (팀 합의 R²=0.8995) |
| [`04_production_shift_official_40pct.png`](figures/04_production_shift_official_40pct.png) | 생산량 유지, 40% 생산시간 분산, 평균 피크 약 1.06% 감소 |
| [`05_region_process_overlap.png`](figures/05_region_process_overlap.png) | 전남·경북·충남의 지역-공정 고부하 시간 중첩률 |
| [`06_demand_variable_correlation_heatmap.png`](figures/06_demand_variable_correlation_heatmap.png) | 전력수요 후보 변수 상관관계 |
| [`07_health_burden_correlation_nonsignificant.png`](figures/07_health_burden_correlation_nonsignificant.png) | 건강부담 상관분석 보조 결과 |

### 3. 세부 분석 Notebook

- [`notebooks/power_facility_overview_presentation_final_review_20260819_executed.ipynb`](notebooks/power_facility_overview_presentation_final_review_20260819_executed.ipynb): 전국 전력시설 공간 분포
- [`notebooks/sido_area_adjusted_demand_infrastructure_v5_final_review_20260819_executed.ipynb`](notebooks/sido_area_adjusted_demand_infrastructure_v5_final_review_20260819_executed.ipynb): 시도별 면적보정 수요·송전 인프라 불균형
- [`notebooks/regional_health_burden_analysis_v2_final_review_20260819_executed.ipynb`](notebooks/regional_health_burden_analysis_v2_final_review_20260819_executed.ipynb): 시도별 건강부담 보조 분석
- [`notebooks/manufacturing_ai_peak_team_clean_export_final_2021_executed.ipynb`](notebooks/manufacturing_ai_peak_team_clean_export_final_2021_executed.ipynb): 제조공정 전력예측 및 생산시간 분산 시뮬레이션

## Notebook에서 지도가 보이지 않을 때

일부 Notebook 뷰어는 Plotly의 대화형 출력 형식(`application/vnd.plotly.v1+json`)을 표시하지 못해 `No renderer could be found`라는 안내를 보여줄 수 있습니다. 이는 분석 코드의 오류가 아니라 뷰어의 렌더러 지원 문제입니다.

심사 및 빠른 결과 확인에는 `figures/`의 정적 PNG/JPEG를 사용하면 됩니다. Notebook은 분석 코드와 실행 결과의 근거로 제공하며, 별도 Marketplace 플러그인 설치 없이도 정적 그림을 열어 결과를 확인할 수 있습니다.

## 해석상 주의

- 부담 점수는 설비용량·선로 부하율이 아닌 지역 간 상대 비교 지표입니다.
- 건강 결과는 지역 단위의 통계적 연관성 탐색이며 인과관계를 의미하지 않습니다.
- 제조공정 데이터는 전남 개별 업체의 실측자료가 아니므로 전남 전체 감축량으로 직접 환산하지 않습니다.
- 따라서 “송전망 부족”이나 “과부하 확정” 대신 “상대적 부담 가능성”과 “수요관리 적용 가능성”으로 해석합니다.

## 공개 범위

이 저장소는 심사위원의 코드·결과 확인을 위한 발표용 패키지입니다. 원본 데이터, 개인 로컬 경로, 인증정보는 포함하지 않았습니다. 수치가 일치하지 않는 중간 시나리오 그림도 공개 목록에서 제외했습니다.

## 저장소 구성

```text
figures/    발표용 정적 결과 그림
notebooks/  실행 결과가 포함된 발표·세부 분석 Notebook
docs/       발표용 파일 안내 및 인수인계 문서
```

추가 안내는 [`docs/15_presentation_handoff.md`](docs/15_presentation_handoff.md)에서 확인할 수 있습니다.
