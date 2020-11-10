# Android ML
## Preview
- https://www.youtube.com/watch?v=PZZJjlyWEQA&list=PLWz5rJ2EKKc9znUgvI7lFPE-v5Vw4mGwG

## ML Kit
 - https://www.youtube.com/watch?v=3RdEIXRgVHo&list=PLWz5rJ2EKKc9znUgvI7lFPE-v5Vw4mGwG&index=2
   - TF Hub(Repository of models)
      - https://tfhub.dev/
      - Model 이 아직 풍부 하진 않음(Resnet50, MobileNet 등등은 다 구비) Quantizered 되어 있는 모델을 선택
   - 
# IDEA
 - 시청 패턴을 활용 한 추천
 - 어떤 컨텐츠를 좋아 하느냐.. 등등
  
# Detr(DEtection TRansformer)
* Link(https://github.com/facebookresearch/detr)
* colab link[https://colab.research.google.com/github/facebookresearch/detr/blob/colab/notebooks/detr_demo.ipynb]

## What
* Given a fixed small set of learned object queries, DETR reasons about the relations of the objects and the global image context to directly output the final set of predictions in parallel. Due to this parallel nature, DETR is very fast and efficient.
* <- 이 부분을 좀 더 명확히 이해가 필요함
<img src="https://user-images.githubusercontent.com/7637498/97835204-fdd7cc00-1d1c-11eb-8a13-68adc2f97303.png"/>



## Benefit
* 빠르고 가볍다?
* 활용도 측면에서 Object detection , Segmentation 도 된다. 
* Global Context 및 Feature 에서 Prediction 하는 거라 Segmentation 과 비슷하다고 볼수 있을 거 같음

## 궁금한점 
- 모든 테스트 셋에 대하여 클래스 


# Transformer
## 개요
  - NLP 연구 방향을 바꿔버린 혁신적인 아키텍쳐(RNN을 폐기)
  - NLP 뿐만 아니라 모든 time series 를 전부 다 다룰수 있음
  - Self-Attention 을 도입, recurrent 한 구조 없이 virialble length temporal dependency 학습 가능하게 만듦
  - 기존 LSTM 에서는 불가능했던 시계열 병렬화()가 가능해짐
     * 훨씬 빠른 학습 속도
     * 매우 깊은 층을 쌓고, 방대한 데이터 학습이 가능 해짐
     * 엄청 성능 증가(BERT) (<- 층을 많이 쌓는게 가능해짐으로써 나온 것)
     
## 사용성
  - 번역기
  - encoder(Input 을 이해하는 역할 ) -> decoder( Input 이해한 것을 바탕으로 Output 생성  )
     * 각각이 의미 있음 encoder 만 사용하는(BERT) decoder 만 사용하는(GPT)
  
## Word Embeding
  - on hot encoding -> 
  - Self Attention 을 통해서 Contextual Word Embeding 이 나옴
  
## Self-Attention(Intra-Attention)
  - 각 단어들이, 문장안의 다른 단어들과 어떤 관계를 가지는 추출
  - NxN
  - Feed Forward NN 은 비선형 적인 
  - 멀리 있는 것도 같이 보는 것
  - 기존 NLP 는 시쿼셜 했음

### 동작
 -  image to sentence lstm 돌면서 생성  CNN -> LSTM 하는 걸 Attention 나옴
 - Attention
    * 피상적으로 이해 하기로는 특정 상태를 이해하기 위해서 그것만 강조 하는 Elephant를 알려면 Elephant 만 알면된다.
    * 강조 되는 포커스를 가한다.
 - Queries -> key -> values 를 구하는 과정
 -
     
     
     
