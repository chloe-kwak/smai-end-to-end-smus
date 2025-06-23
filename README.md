# SageMaker Unified Studio에서 진행하는 SageMaker AI ML 엔드투엔드 워크플로우

이 프로젝트는 Amazon SageMaker와 MLflow를 활용한 완전한 머신러닝 워크플로우를 구현합니다. 은행 마케팅 데이터셋을 사용하여 고객의 정기예금 가입 여부를 예측하는 분류 모델을 개발합니다.

## 📋 프로젝트 구조

### 1. **환경 설정** (`0-setup.ipynb`)
   - AWS 환경 및 권한 설정
   - SageMaker AI 프로젝트 초기화
   - MLflow 추적 서버 연결
   - 데이터 준비 및 기본 탐색
   - 실험 환경 초기화

### 2. **데이터 전처리** (`1-preprocessing.ipynb`)
   - SageMaker Processing Job을 사용한 대규모 데이터 전처리
   - 특성 엔지니어링 및 원-핫 인코딩
   - 훈련/검증/테스트 데이터 분할
   - MLflow를 통한 전처리 과정 추적

### 3. **모델 훈련** (`2-training.ipynb`)
   - SageMaker Training Job을 사용한 모델 훈련
   - XGBoost 알고리즘 활용
   - 하이퍼파라미터 튜닝
   - Script Mode를 통한 커스텀 훈련
   - MLflow를 통한 모델 등록 및 실험 추적

### 4. **모델 성능 평가** (`3-model-evaluation.ipynb`)
   - 훈련된 모델의 로컬 테스트
   - 모델 성능 비교 및 분석
   - 혼동 행렬 및 분류 리포트 생성
   - MLflow를 통한 실험 추적 및 시각화
   - 최고 성능 모델 선택

### 5. **모델 배포 및 테스트** (`4-test-and-deploy.ipynb`)
   - SageMaker 모델 등록
   - 실시간 엔드포인트 배포
   - A/B 테스트를 위한 멀티 모델 배포
   - 트래픽 분산 및 가중치 조정
   - 배포된 모델 테스트

### 6. **ML 파이프라인** (`5-pipelines.ipynb`)
   - SageMaker 파이프라인을 사용한 엔드투엔드 자동화
   - 데이터 전처리, 모델 훈련, 평가, 배포 자동화
   - 조건부 모델 등록
   - 파이프라인 실행 및 모니터링
   - CI/CD 워크플로우 구축

## 🚀 주요 기능

### SageMaker 통합 환경
- **SageMaker AI 프로젝트**: 통합된 리소스 관리 및 협업
- **MLflow 통합**: 실험 추적, 모델 버전 관리, 아티팩트 저장
- **자동화된 워크플로우**: Processing → Training → Evaluation → Deployment 파이프라인

### 데이터 처리 및 모델링
- **확장 가능한 전처리**: SageMaker Processing으로 대용량 데이터 처리
- **분산 훈련**: SageMaker Training Job을 통한 효율적인 모델 훈련
- **하이퍼파라미터 최적화**: 자동화된 하이퍼파라미터 튜닝
- **실시간 추론**: SageMaker 엔드포인트를 통한 실시간 예측

### 실험 관리 및 모니터링
- **실험 추적**: MLflow를 통한 모든 실험 기록
- **모델 비교**: 다양한 모델 성능 비교 및 선택
- **아티팩트 관리**: 모델, 데이터, 코드의 버전 관리

## 📊 사용 데이터

**은행 마케팅 데이터셋 (Bank Marketing Dataset)**
- **목표**: 고객의 정기예금 가입 여부 예측 (이진 분류)
- **특성**: 고객 정보, 연락 정보, 경제 지표 등 21개 특성
- **데이터 크기**: 41,188개 샘플
- **클래스 불균형**: 약 11% 양성 클래스 (정기예금 가입)

## 🛠️ 기술 스택

- **AWS SageMaker**: ML 플랫폼 및 관리형 서비스
- **MLflow**: 실험 추적 및 모델 관리
- **Python**: 데이터 처리 및 모델링
- **Scikit-learn**: 머신러닝 라이브러리
- **XGBoost**: 그래디언트 부스팅 알고리즘
- **Pandas/NumPy**: 데이터 조작 및 분석

## 📈 학습 목표

이 프로젝트를 통해 다음을 학습할 수 있습니다:

1. **SageMaker 서비스 활용**: Processing, Training, Hosting 서비스 사용법
2. **MLOps 실습**: 실험 추적, 모델 버전 관리, 자동화된 파이프라인
3. **확장 가능한 ML**: 클라우드 환경에서의 대규모 ML 워크플로우
4. **모범 사례**: 코드 구조화, 실험 관리, 배포 전략

## 🚦 시작하기

1. **환경 설정**: `0-setup.ipynb` 실행
2. **데이터 전처리**: `1-preprocessing.ipynb` 실행  
3. **모델 훈련**: `2-training.ipynb` 실행
4. **모델 평가**: `3-model-evaluation.ipynb` 실행
5. **모델 배포**: `4-test-and-deploy.ipynb` 실행
6. **파이프라인 구축**: `5-pipelines.ipynb` 실행

각 노트북은 순차적으로 실행되도록 설계되었으며, 이전 단계의 결과를 다음 단계에서 활용합니다.

## 📝 참고사항

- 이 프로젝트는 AWS SageMaker Studio 환경에서 최적화되어 있습니다.
- MLflow 추적 서버가 필요하며, 설정은 `0-setup.ipynb`에서 수행합니다.
- 모든 AWS 리소스는 사용 후 정리하는 것을 권장합니다.
