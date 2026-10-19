# 10월 19일
# MLFlow 2

## 머신러닝 실험
- 모델의 성능을 개선하거나 다양한 설정을 비교 분석하기 위해 반복적으로 수행하는 과정 중심으 ㅣ실험 활동
- 즉 "어떤 데이터를 써서", "어떤 알고리즘에", "어떤 하이퍼파라미터를 적용했더니", "어떤 결과가 나왔는지" 체계적으로 비교하는 작업

### **왜 실험이 중요한가?**
- 머신러닝에서는 하나의 정답이 존재하지 않고, 여러 조건에 따라 성능이 달라지기 때문에 실험이 필수적

- 데이터셋 : 전처리 방식에 따라 결과가 크게 달라질 수 있으므로 데이터 범위 버전, 분할, 전처리

- 모델 구조 : 동일한 데이터에도 모델 구조가 성능에 영향

- 하이퍼파라미터 : 학습률, 에폭 수, 정규화 강도 등

- 성능 지표 : Accuracy, F1 Score, AUC 등 문제 목적에 맞춘 평가 기준

## **반복 실험의 문제점**
- 엑셀에 기록하다 보면 어느 실험이 어떤 설정인지 까먹음
- 실수로 같은 실험을 중복 진행하거나, 더 좋은 모델을 잃어버림
- 여러 명이 협업할 때 "이 모델이 어디서 나온거지"라는 상황 발생

### **재현성(Reqroducibilty)의 문제**
  - 이 모델이 왜 잘 나왔는지, 다시 만들 수 있을까?

### **버전 관리의 문제**
  - 이 모델, 어떤 코드 버전에서 나온 거였지?

### **협업의 문제**
  - 동료가 만든 모델, 어떻게 학습된건지 모르겠는데..

### **비효율적인 반복 작업**
  - 똑같은 실험, 이미 했던 상황

### **성능 측정 및 비교의 어려움**
  - 결국 어떤 모델이 제일 좋았는지 알 수 없는 경우

## **실험 추적 및 관리 도구**
**실험 추적 도구의 필요성**
- 반복 실험에서 발생하는 문제를 해결하기 위함
- 실험마다 사용된 코드, 데이터, 하이퍼파라미터, 성능지표를 자동으로 기록
- 실험 결과를 비교 분석할 수 있는 인터페이스 필요

**실험 환경 자동화의 필요성**
- 실험은 단순 로깅을 넘어서, 재현 가능한 환경에서 실행되어야 함

**실험 추적 + 모델 저장 + 서빙까지 지원하는 통합 도구 : MLFlow**
- MLFlow는 오픈 소스로 제공되는 머신러닝 실험 관리 플랫폼
- 다양한 프레임워크와 호환성이 좋음
- 실험 로그 관리 뿐 아니라 모델 저아, 등록, 서빙까지 한번에 가능

## **MLFlow Tracking을 활용한 실험 관리 전략**

### **실험 관리 전략**
- 실험을 체계적으로 계획하고 수행하고 비교 분석하는 전 과정
- 실험 목표 -> 고정할 데이터, 평가방식 -> 바꿀 조건 ->Run 단위 -> 기록 규칙
- 예시로 실험 목적에 따른 실험 공간을 분리해서 관리할 수 있음

### **실험 결과 저장 위치 구조**
- MLFlow는 실험 데이터를 디렉토리에 저장
- 로컬 저장 기준이며, 백엔드 저장소를 바꾸면 DB/S3 등에 저장 가능
- 추가로 MLFlow UI에 접속하여 해당 RUN을 클릭하면 파일 구조를 확인 가능

### **실험 단위 구분**
- Experiment : 동일한 목적의 실험들을 묶는 상위 단위
- Run : 한 번의 학습, 평가, 실행 단위
- 하이퍼파라미터는 Params, 결과는 Metrics, 추가 정보는 tags로 기록
- 학습된 모델은 Run과 연결된 Logged Model로 관리
- MLFlow 3.x 에서 Logged Model에 m-... 형태도 별도 Model ID 부여됨

### **커스텀 로깅**
- MLFlow는 기본 로깅 외에도 내가 원하는 정보를 자유롭게 추가 가능
- MLFlow.log_param() : 하이퍼파라미터나 실행 설정 기록
- MLFlow.log_metric() : 평가 지표나 학습 중 수치 기록
- MLFlow.log_tag() : 실험 목적, 전처리 방식, 데이터버전 등 부가 정보 기록
- MLFlow.set_tag() : 실험 목적, 전처리 방식, 데이터 버전 등 부가 정보 기록
- MLFlow.log_artifact() : 그래프 리포트, 설정 파일 등의 결과물 저장

### **실험 정보 구조화**
- MLFlow는 실행 정보를 Params, Metric, Tags, Artifacts로 구분해 기록
- 각 정보는 실험 비교, 분석, 재현성 확보에 활용
- Params -> 학습 설정 및 하이퍼파라미터
- Metrics -> 평가 지표 및 학습 결과
- Tags -> 실행 목적, 데이터/ 전처리 정보 등 메타데이터
- Artifacits -> 그래프, 리포트, 설정 파일 등 결과물

### **실험 태그 및 노트 관리 방법**
- UI와 API에서 태그 기반 검색이 가능함 -> 실험 분류/ 필터링에 유용
- MLFlow는 Run에 Key-value 형태의 태그를 추가해 메타 정보를 관리할 수 있음

### **반복 실험 로깅과 Artifact 관리**
- Grid Search나 반복 학습에서는 각 실행 결과를 별도의 Run으로 기록
- Run 별로 params, metrics, tags를 저장해 조건과 성능을 비교
- ROC curve, confusion matrix 등의 시각화 결과는 Artifact로 저장 가능
- 반복 실험이 많을수록 로깅 코드는 함수화하거나 자동화 하는 것이 유용
- 저장된 Artifact는 MLFlow UI에서 Run 별로 확인 가능

### **실험 비교 전략**
- MLFlow UI에서 Run을 필터링 및 정렬하여 원하는 실험을 빠르게 탐색
- params, metrics, tags를 기주능로 Run간의 차이를 비교
- 여러 Run의 Metric을 차트로 시각화하여 성능 변화를 확인
- 최고 성능뿐 아니라 어떤 설정이 결과에 영향을 주었는지 함께 분석

### **실험 검색 / 비교 예시**
- 기본 Experiment는 Default이며 일반적으로 ID 0
- 새 Experiment를 생성하면 고유한 experiment_id가 부여됨
- search_runs()에서 하나 이상의 Experiment를 대상으로 Run 검색 가능

### **실험 조건 정의**
- 반복할 하이퍼파라미터 값을 YAML 파일에 정의
- 실험 조건을 코드와 분리해 관리하면 수정, 재사용이 쉬움
- 이후 Python 코드에서 설정을 읽어 여러 Run을 생성할 수 있음

### **실험 자동화 흐름 예시**
- itertools.product()를 사용해 모든 하이퍼파라미터 조합 생성
- 각 조합마다 모델을 학습하고 MLFlow Run으로 기록
- 파라미터 조합 수가 많아질수록 자동화된 반복 실행이 유용

- MLFlow.start_run() 블록 안에서 파라미터와 결과를 자동으로 로깅
- 각 조합에 대해 하나의 실험(run)이 생성되며, 비교/시각화에 활용

## **실험 관리 전략 팁**
- MLFlow는 실험 실행 정보를 추적하고 비교하기 위한 플랫폼
- Experiment -> Run -> Params / metrics / tags / artifacts 구조를 일관되게 관리
- 반복 가능한 실험을 위해 코드, 파라미터, 데이터 버전, 결과를 함께 기록

- 실험 관리 시 유용한 팁 3가지
  - Run 이름은 실험 목적이나 핵심 변경점 중심으로 작성
  - 세부 조건은 Run이름에 모두 넣기보다 params와 tags로 기록
  - MLFlow.search_runs()로 여러 Run을 DataFrame 형태로 조회, 분석

### **MLFlow 모델 관리 및 배포**
- 모델 버전 관리
  - MLFlow에서는 하나의 모델 이름 아래 여러 버전의 모델을 등록할 수 있음
  - Alias 방식이 도입되면서, 자유로운 문자열로 여러 버전으로 저장 가능

- Alias
  - 여러 Alias가 동일한 Version을 가리킬 수 있음
  - 하나의 Alias가 가리키는 Version을 다른 Version으로 쉽게 변경 가능
  - champion, cadidate 등의 이름으로 모델의 역할을 표현 가능

### **MLFLow models 구조**
- MLFlow Model은 모델과 실행에 필요한 메타정보를 함께 저장하는 표준 포멧
  - Flavor를 통해 Scikit-learn, XGBoost, TensorFlow/Keras 등 다양한 모델 형식을 지원
  - 학습된 모델을 Logged Model이라는 독립적인 엔티티로 관리
  - 모델 파일뿐 아니라 의존성, 입력 형식, Signature 등의 정보도 함께 저장 가능

- MLFlow Model로 저장하는 이유
  - MLFlow Model은 모델과 함께 실행 환경 및 모델 메타정보를 관리
  - MLmodel에 Flavor, Signature, 모델 메타정보 등이 기록됨
  - requirements.txt, conda.yaml, python_env.yaml 등을 통해 실행 환경 재구성에 활용
  - 저장된 모델을 로딩, Registry 등록, Serving 등의 후속 과정에 일관된 방식으로 사용 가능

### **MLFlow 모델 저장 방법**
- 모델 저장 방법
  - log_model()을 사용해 학습된 모델을 MLFlow Model 형식으로 기록
  - 모델 파일을 함께 Flavor, 의존성, Signature, 입력 예시 등의 정보 저장 가능
  - 저장된 모델을 MLFlow UI에서 확인 가능하고 Registry 등록이나 추론에 활용 가능

- 저장된 모델 불러오기
  - Model ID를 이용해 특정 Logged Model을 직접 불러올 수 있음
  - Registry에 등록했다면, Model Version이나 Alias를 기준으로 불러올 수도 있음
  - MLFlow.pyfunc.load_model()을 사용하면 Flavor에 관계없이 공통 인터페이스로 로딩 가능

- MLFlow 저장소 구성
  - MLFlow 서버는 메타데이터와 Artifact를 서로 다른 저장소에 저장 가능
  - backend-store-url  
  -> Experiment, Run, Params, Metircs, Tags, Model Registry 등의 메타데이터 저장
  - Artifact Store  
  -> 모델 파일, 이미지, 리포트 등의 파일형 Artifact 저장
  - 로컬 환경에서는 SQLite + 로컬 디렉토리 조합을 간단히 사용할 수 있음
  - 팀/운영 환경에서는 PostgreSQL/MySQL + Object Storage 등의 조합을 주로 사용

### **모델 관리 및 배포**
- 모델 Signature 활용
  - MLmodel 파일에는 모델 Flavor, Signature 등 모델 메타정보가 기록됨
  - Signature는 모델의 입력/출력 스키마를 정의
  - Signature를 저장하면 추론 시 입력 데이터의 구조와 타입을 검증하는 데 활용 가능
  - 배포 및 서빙 환경에서 모델 인터페이스를 명확하게 유지하는 데 유용

- 모델 관리 배포의 흐름
  - 실험 -> 모델 기록 -> 검증/등록 -> 추론
  - 학습 결과 중 사용할 모델을 선택하고, Logged Model 및 Registry를 통해 관리
  - 운영 코드에서는 특정 버전 번호 대신 Alias를 이용해 모델을 불러올 수 있음

### **모델 배포 전략**
- 로컬 환경에서 API로 서빙하기
  - MLFlow 서빙 명령어를 통해 배포 가능
```bash
mlflow models serve \
  -m "models:/Practice2_ChurnModel@champion" \
  -p 5001
```

- 기본구성
  - RESTful API 형식
  - \invocaltions 엔드포인트로 JSON 데이터로 POST

### **MLFlow 모델 서빙**
- MLFlow Model을 추론 가능한 형태로 실행하는 기능
- 저장된 모델을 REST API 서버로 실행해 외부에서 예측 요청 가능

### **MLFlow 모델 서빙 환경 및 확장성
- 서빙 환경 고려사항
  - 입출력 형식 : Signature 미지정 시 예측 요청 에러 발생 가능
  -> 입력 스키마 명확히 저장 필요
  - 동시 요청 처리 : 기본 서버는 단일 스레드 -> 실무 배포 시 gunicon, uvicorn 등 활용 권장
  - Docker 서빙 : MLFlow models build-docker 명령으로 모델을 컨테이너화 이식성 향상

- MLFlow Models의 확장성
  - 다양한 프레임워크 지원 : scikit-learn, tensorflow, xgboost, pytorch 등과 연동 가능
  - 이식성 : Databricks, AWS SageMaker 등 다양한 플랫폼에 배포 가능
  - 모델 관리 연계 : 추후 Model Registry, 서빙 인프라 (API Gateway 등)와 자연스럽게 연결됨
  - 통합 구조 : 모델 저장 -> 로딩 -> 배포까지 하나의 포맷으로 처리 가능(MLmodel + artifact)

## 모델 관리 및 배포 실습
- 목표
  - 와인 품질 데이터셋으로 회귀 모델 학습
  - 학습된 모델을 Logged Model로 저장
  - REST API 형태로 모델 배포

- 실험 내용
  - 데이터셋 : 와인품질
  - 데이터셋 모델 : LinearRegression
  - wine-quality-model 이름으로 Model Registry에 등록
  - 등록된 버전에 champion Alias 지정

- 실험 포인트
  - Experiment와 Run을 생성해 학습 결과 추적
  - params, metrics를 Run에 기록
  - log_model()로 모델을 Logged Model로 저장
  - Logged Model을 Model Registry에 등록
  - Alias를 사용해 사용할 모델 버전을 명확하게 지정

























