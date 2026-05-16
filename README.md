# LSTM AutoEncoder 기반 금융 이상거래 탐지 시스템 개인프로젝트 최종보고서(PDF)
(https://github.com/user-attachments/files/27863199/201969022._.pdf)

## 프로젝트 개요

본 프로젝트는 금융 데이터의 심각한 불균형 문제와 실제 금융 환경에서 이상 거래 레이블 데이터를 충분히 확보하기 어렵다는 한계를 해결하기 위해 진행한 개인 프로젝트입니다.

기존 지도학습 기반 Fraud Detection System(FDS)의 한계를 보완하기 위해 자기지도학습(Self-Supervised Learning) 기반의 LSTM AutoEncoder 모델을 활용하여 이상 금융거래를 탐지하였습니다.

또한 모델의 설명 가능성과 학습 효율성을 향상시키기 위해 SHAP 기반 변수 선택(XAI) 기법과 CTGAN 기반 데이터 증강 기법을 함께 적용하였습니다.

---

## 주요 기능 및 연구 내용

- LSTM AutoEncoder 기반 이상탐지 모델 구현
- SHAP Value 기반 변수 중요도 분석 및 Feature Selection
- CTGAN 기반 금융 이상 데이터 오버샘플링
- 시계열(Time-Series) 기반 이상거래 탐지
- Window Sliding / Non-overlapping 방식 비교 실험
- 다양한 하이퍼파라미터 실험 및 성능 비교
- Precision / Recall / F1-Score 기반 성능 평가

---

## 사용 데이터셋

- Kaggle Credit Card Fraud Detection Dataset
- 약 28만 건의 거래 데이터 활용
- 이상 거래 비율 약 0.172% 수준의 극단적 불균형 데이터셋

---

## 사용 기술 스택

- Python
- TensorFlow / Keras
- SHAP
- CTGAN
- Scikit-learn
- Pandas / NumPy
- Matplotlib

---

## 프로젝트 목표

실제 금융 환경에서는 이상 거래(Fraud) 데이터 확보가 어렵고 레이블링 비용 또한 매우 높습니다.

본 프로젝트는 정상 거래 데이터만을 활용하여 정상 패턴을 학습하고, 재구성 오류(Reconstruction Error)를 기반으로 이상 거래를 탐지하는 AutoEncoder 구조를 활용하였습니다.

또한 설명 가능한 AI(XAI) 기법을 적용하여 모델 해석 가능성과 컴퓨팅 효율성을 동시에 개선하고자 하였습니다.

---

## 연구 결과

실험 결과, 다음 조건에서 가장 높은 성능을 기록하였습니다.

- SHAP 기반 변수 선택 적용
- Non-overlapping 시퀀스 생성 방식 적용
- Dropout 적용
- TimeSteps = 10

### 최고 성능
- F1-Score : **0.7184**

실험을 통해 다음과 같은 점을 확인할 수 있었습니다.

- 불필요한 특성은 재구성 오류를 불안정하게 만들 수 있음
- SHAP 기반 변수 선택은 학습 효율성과 성능 향상에 기여함
- 시계열 길이에 따라 최적의 변수 선택 전략이 달라질 수 있음

---

## 프로젝트 의의

본 프로젝트는 단순 모델 구현을 넘어 다음과 같은 부분에 중점을 두었습니다.

- 금융 도메인 기반 이상탐지 연구
- Explainable AI(XAI) 활용
- 데이터 불균형 문제 해결
- 시계열 기반 이상탐지 실험
- 다양한 하이퍼파라미터 및 구조 비교 분석
- 실제 금융 환경 적용 가능성 탐색

---

## 향후 발전 방향

- 실시간 스트리밍 기반 이상탐지 시스템 확장
- Redis 및 FastAPI 기반 실시간 탐지 파이프라인 구축
- 금융 도메인 지식 기반 Feature Engineering 적용
- SHAP 계산 모델 최적화
- Explainable AI 기반 금융 리스크 시각화 시스템 연계
