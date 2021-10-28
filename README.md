# Project 6-2
---
## Goal

 - 문서 이미지의 주요값 인식

    1) 딥러닝 네트워크를 활용하여 문서 이미지 회전 각도를 예측하는 모델 학습

       (합성 데이터 11,948 활용 - train, validation 나눠 활용)

       (학습시 이미지를 실제 test 데이터와 분포를 유사하게 맞추는게 중요)

       (학습데이터 추가적 합성 허용)

       (val : 99% , test 95%)


---
### 작업 노트

---

21/10/26
데이터 - 합성 이미지 11,948

data 링크  
https://drive.google.com/file/d/1Byk5fABsGdYWlSuKzXwieQO_4KP0Uk_t/view?usp=sharing

---

21/10/27
연구방법 서칭

문서1) 이미지 인식률 개선을 위한 CNN 기반 이미지 회전 보정 알고리즘

문서2) BYOL - 자가지도 학습 (기존 자가지도 학습의 문제점을 해결)
https://yuhodots.github.io/deeplearning/21-04-04/

참고사이트

기울기 보정 알고리즘  
https://ichi.pro/ko/opencvleul-sayonghayeo-tegseuteu-imijileul-jadong-eulo-giulgi-bojeong-ttogbalo-haneun-bangbeob-176759562404831

