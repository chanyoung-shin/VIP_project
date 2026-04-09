# 프로젝트 개요

## 데이터
- **주요 데이터**: `extracted_variables.csv` — NHIS(국민건강보험) 데이터에서 추출한 변수들
- **변수 설명서**: `NHIS Questionnaire_Cancer and LM (5).xlsx` — 각 변수에 대한 설명 포함

## 프로젝트 목표
변수 유형에 맞는 결측치(Missing Value) 처리:
- **명목형 변수 (Nominal)**: 최빈값(mode) 등 범주형에 적합한 방법으로 처리
- **순서형 변수 (Ordinal)**: 중앙값(median) 등 순서 특성을 고려한 방법으로 처리
- **연속형 변수 (Continuous)**: 평균(mean), KNN, 회귀 등 수치형에 적합한 방법으로 처리

---

# 협업 규칙

> **코드를 생성하거나 수정하기 전에는 반드시 사용자의 허락을 받은 뒤에 최종적으로 변경한다.**
