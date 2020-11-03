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
