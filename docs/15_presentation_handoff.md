# 발표용 파일 전달 안내

## 목적

심사위원에게 제공할 Notebook과 발표자료 제작에 사용할 핵심 결과를 한 곳에서 안내한다.

## 권장 공개 파일

### 1. 통합 Notebook

- 파일: [`../notebooks/presentation_final_analysis_executed.ipynb`](../notebooks/presentation_final_analysis_executed.ipynb)
- 용도: 전력시설 현황, 수요·면적보정 인프라 불균형, 건강부담 보조 분석, 제조공정 수요관리 결과를 한 번에 확인
- 상태: 실행 결과 포함, 코드 셀 오류 0건, 그래프 출력 포함

이 파일을 GitHub 링크 또는 QR코드의 기본 대상으로 사용한다.

### GitHub/VS Code에서 Plotly 지도가 안 보일 때

일부 Notebook 뷰어는 Plotly 대화형 출력(`application/vnd.plotly.v1+json`)을 렌더링하지 못해 `No renderer could be found` 안내를 표시할 수 있다. 이는 분석 실패가 아니라 뷰어 지원 문제다. 심사위원은 `../figures/`의 정적 PNG/JPEG에서 결과를 바로 확인할 수 있으며, Notebook은 코드와 실행 결과의 근거로 사용한다.

### 2. 세부 작업 파일의 보관

세부 분석 Notebook과 중간 실행 파일은 개인 작업 폴더에 보존한다. 공개 저장소에는 심사위원이 분석 흐름과 실행 결과를 빠르게 확인할 수 있도록 통합 실행본 1개만 제공한다.

## 발표 핵심 결과

- 면적보정 수요·인프라 비교: 전남·경북·충남이 상대적 부담 가능성 상위 지역
- 건강부담: 시도 단위 분석에서 통계적으로 유의한 관계가 확인되지 않아 보조 결과로 해석
- 제조공정 시뮬레이션: 생산량 유지, 40% 생산시간 분산 시 평균 피크 약 1.06% 감소
- 시간대 적용 근거: 전남 지역 전력 고부하 시간과 제조공정 고부하 시간의 중첩률 80%

## 발표용 그림 파일

발표자료에 포함된 그림은 [`../figures/`](../figures/)에서 확인할 수 있다.

- [`01_nationwide_power_facilities_map.jpeg`](../figures/01_nationwide_power_facilities_map.jpeg): 전국 전력시설 위치 분포
- [`02_sido_demand_index.png`](../figures/02_sido_demand_index.png): 시도별 수요지수
- [`03_manufacturing_model_performance.png`](../figures/03_manufacturing_model_performance.png): 제조공정 전력예측 성능, 팀 합의 R²=0.8995
- [`04_production_shift_official_40pct.png`](../figures/04_production_shift_official_40pct.png): 40% 생산시간 분산 결과(137.47 → 135.40, 약 1.06% 감소)
- [`05_region_process_overlap.png`](../figures/05_region_process_overlap.png): 전남·경북·충남의 지역-공정 고부하 시간 중첩률
- [`06_demand_variable_correlation_heatmap.png`](../figures/06_demand_variable_correlation_heatmap.png): 수요 변수 상관관계 보조 그림
- [`07_health_burden_correlation_nonsignificant.png`](../figures/07_health_burden_correlation_nonsignificant.png): 건강부담 상관분석 보조 그림(p=0.093503, 유의하지 않음)

그림은 발표자료와 결과 확인을 위한 보조 산출물이다. 코드와 실행 결과가 있는 Notebook이 재현성의 기준이며, 그림만으로 설비용량이나 실제 선로 부하율을 주장하지 않는다. 수치가 일치하지 않는 중간 그림은 공개 목록에서 제외했다.

정적 그림은 발표 결과 확인의 기준으로 사용할 수 있다. Notebook에서 Plotly 출력이 렌더링되지 않더라도 이는 뷰어 한계이며 분석 오류가 아니다.

## 해석상 주의

- 부담 점수는 설비용량이나 선로 부하율이 아닌 상대 비교 지표다.
- 건강 결과는 지역 단위 통계적 연관성 탐색이며 인과관계를 의미하지 않는다.
- 제조공정 데이터는 전남 개별 업체의 실측자료가 아니므로 전남 전체 감축량으로 환산하지 않는다.
- “송전망 부족” 또는 “과부하 확정” 대신 “상대적 부담 가능성”이라고 표현한다.

## 확인 기록

- 통합 Notebook 코드 셀: 8개 실행
- 통합 Notebook 오류: 0건
- 결론 Markdown 셀: 발표용 문안 반영
- 발표용 그림: 7개 포함
- 그림·Notebook·발표 수치 연결 확인 완료
- Plotly 렌더러 제한 및 정적 그림 확인 경로 문서화
