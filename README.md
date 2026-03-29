## 프로젝트 개요
과제 2: Baseline 모델링 & Versioning
Titanic 데이터셋을 사용하여 전처리, 모델링, 버전관리를 포함한 재현 가능한 머신러닝 실험 구조를 구현.

## 실험 목표
- KNN과 SVM 성능 비교
- Scaling과 Encoding의 영향 확인
- `Pipeline`과 `ColumnTransformer` 구조 구현
- Git 기반 실험 관리
- DVC의 역할에 대한 간단한 회고 정리

## 데이터셋
Titanic 데이터셋은 승객의 생존 여부를 예측하는 이진 분류 문제

- Target: `Survived`
- 수치형 변수와 범주형 변수가 함께 존재
- `Age`, `Embarked` 등 일부 결측치 존재

## 전처리 구조
Titanic 데이터는 수치형과 범주형 데이터가 혼합되어 있기 때문에 `ColumnTransformer`를 사용함.

- 수치형 변수: 결측치 대체 + Scaling
- 범주형 변수: 결측치 대체 + One-hot Encoding
- 전체 구조: `ColumnTransformer` → `Pipeline` → 모델

## 실험 내용
다음 실험을 수행함.

1. SVM (No Scaling)
2. StandardScaler + SVM
3. StandardScaler + KNN
4. MinMaxScaler 비교 (선택)

## 프로젝트 구조
```bash
baseline-titanic/
├── data/
├── notebooks/
├── src/
├── results/
├── README.md
└── requirements.txt