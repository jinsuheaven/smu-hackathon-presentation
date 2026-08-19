# 발표용 파일 전달 안내

## 목적

심사위원에게 제공할 Notebook과 발표자료 제작에 사용할 핵심 결과를 한 곳에서 안내한다.

## 권장 공개 파일

### 1. 통합 Notebook

- 파일: [`../notebooks/presentation_final_analysis_executed.ipynb`](../notebooks/presentation_final_analysis_executed.ipynb)
- 용도: 전력시설 현황, 수요·면적보정 인프라 불균형, 건강부담 보조 분석, 제조공정 수요관리 결과를 한 번에 확인
- 상태: 실행 결과 포함, 코드 셀 오류 0건, 그래프 출력 포함

이 파일을 GitHub 링크 또는 QR코드의 기본 대상으로 사용한다.

### 2. 세부 근거 Notebook

필요할 때 통합 Notebook의 각 분석을 자세히 확인하기 위한 파일이다.

- [`../notebooks/power_facility_overview_presentation_final_review_20260819_executed.ipynb`](../notebooks/power_facility_overview_presentation_final_review_20260819_executed.ipynb)
- [`../notebooks/sido_area_adjusted_demand_infrastructure_v5_final_review_20260819_executed.ipynb`](../notebooks/sido_area_adjusted_demand_infrastructure_v5_final_review_20260819_executed.ipynb)
- [`../notebooks/regional_health_burden_analysis_v2_final_review_20260819_executed.ipynb`](../notebooks/regional_health_burden_analysis_v2_final_review_20260819_executed.ipynb)
- [`../notebooks/manufacturing_ai_peak_team_clean_export_final_2021_executed.ipynb`](../notebooks/manufacturing_ai_peak_team_clean_export_final_2021_executed.ipynb)

## 발표 핵심 결과

- 면적보정 수요·인프라 비교: 전남·경북·충남이 상대적 부담 가능성 상위 지역
- 건강부담: 시도 단위 분석에서 통계적으로 유의한 관계가 확인되지 않아 보조 결과로 해석
- 제조공정 시뮬레이션: 생산량 유지, 40% 생산시간 분산 시 평균 피크 약 1.06% 감소
- 시간대 적용 근거: 전남 지역 전력 고부하 시간과 제조공정 고부하 시간의 중첩률 80%

## 해석상 주의

- 부담 점수는 설비용량이나 선로 부하율이 아닌 상대 비교 지표다.
- 건강 결과는 지역 단위 통계적 연관성 탐색이며 인과관계를 의미하지 않는다.
- 제조공정 데이터는 전남 개별 업체의 실측자료가 아니므로 전남 전체 감축량으로 환산하지 않는다.
- “송전망 부족” 또는 “과부하 확정” 대신 “상대적 부담 가능성”이라고 표현한다.

## 확인 기록

- 통합 Notebook 코드 셀: 8개 실행
- 통합 Notebook 오류: 0건
- 결론 Markdown 셀: 발표용 문안 반영
- 상세 수치와 출처: [`14_presentation_results_summary.md`](14_presentation_results_summary.md)
