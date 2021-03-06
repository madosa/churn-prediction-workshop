## 워크샵 사전 준비 사항

에벤트 엔진, 세이지 메이커 노트북 설치, 소스 다운로드를 위해서 아래를 클릭해서 진행 해주세요.
- **사전 준비 사항**: [여기](prerequisite/Prerequisite.md)
- **노트북 1.0, 2.0, 3,0, 4.0 을 실행하시면 워크샵 완료 입니다.**
- 참고 및 옵션으로서 노트북 9.0 은 2.0, 4.0 을 결합한 버전으로 log-prpreprocessing.py을 사용하여 추론시 로그를 남기어서 Inferenece pipeline이 어떻게 작동하는지를 확인하게 합니다. **노트북 9.1이 prpreprocessing.py를 설명하면서 Inferenece pipeline를 설명 합니다.**


# 고객 이탈 예측 모델 및 평가 (Churn Prediction Model)
- 실제 미국 이동 통신 회사의 고객 데이타를 가지고 모델 학습 및 평가 함.
- This content is mostly in Korean. Please let me know if you need in english

## 비즈니스 배경 (Business Background)

고객을 잃는 다는 것은 어느 기업이나 손실이 큽니다. **불만이 있는 고객을 미리 인지한다는 것은, 미리 이탈 방지 할 수 있는 여러 프로모션을 줄 수 있는 기회를 제공** 합니다. 머신 러닝은 데이타를 통해서 이런 이탈 고객을 예상할 수 있는 방법을 제공 합니다. 물론 머신 러닝이 100% 정확한 예상을 할 수는 없지만, 이탈에 영향을 주는 의미 있는 데이타를 확보할 경우에는 예측 정확도는 상당히 올라 갑니다. 이런 모델을 통해서 고객 이탈 방지할 수 있는 가치를 제공 할 수 있습니다.

## 기술적 내용 (Technical Coverage)
본 노트북들은 아래와 같은 기술적인 요소를 포함 합니다.
- 피쳐 생성 (Feature Transformer): SageMaker Processing 
    - 원본 데이타에 전처리 로직을 적용하여 전처리 데이타를 만드는 기술
- 모델 학습: SageMaker Built-in XGBoost Algorithm 사용
- **Inference Pipeline: '전처리 --> 모델 추론 -> 후처리' 로 파이프라인 생성**
    - ![Inference Pipeline](img/Fig2.2.inference_pipeline.png)
- 배치 추론: SageMaker Batch Transform 사용하여 추론
    - 모델 평가: Confusion Matrix를 생성하여 F1, Precision, Recall, Accuracy 확인
- 실시간 추론: SageMaker Realtime Endpoint 사용하여 추론



- 이 워크샵은 아래 블로그들을 참조하여 작성을 함.
## Reference:
    * Blog: Visualizing Amazon SageMaker machine learning predictions with Amazon QuickSight
        * https://aws.amazon.com/blogs/machine-learning/making-machine-learning-predictions-in-amazon-quicksight-and-amazon-sagemaker/
        * Git
            * https://github.com/aws-samples/quicksight-sagemaker-integration-blog
            
    * Blog: Preprocess input data before making predictions using Amazon SageMaker inference pipelines and Scikit-learn
        * https://aws.amazon.com/blogs/machine-learning/preprocess-input-data-before-making-predictions-using-amazon-sagemaker-inference-pipelines-and-scikit-learn/
        * Git: Inference Pipeline with Scikit-learn and Linear Learner
            * https://github.com/awslabs/amazon-sagemaker-examples/blob/master/sagemaker-python-sdk/scikit_learn_inference_pipeline/Inference%20Pipeline%20with%20Scikit-learn%20and%20Linear%20Learner.ipynb

