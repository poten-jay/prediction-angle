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

---

21/10/29

[기울기 보정 알고리즘] 사이트 기본 정리

---

21/10/30

숫자 회전각 학습
https://kr.mathworks.com/help/deeplearning/ug/train-a-convolutional-neural-network-for-regression.html


글 회전각 좌표
https://lee-mandu.tistory.com/520?category=838684

회전 각에 대한 빈영역 구현
https://blog.nerdfactory.ai/2020/09/10/image-augmentation-for-object-detection.html


https://zephyrnet.com/ko/%EB%94%A5-%EB%9F%AC%EB%8B%9D%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EC%9E%90%EB%8F%99-%ED%9A%8C%EC%A0%84/


파이썬 이미지 회전 각도 조절
https://ansan-survivor.tistory.com/954


 - 아이디어 노트

 이미지 중심점 기준 회전 = 대각선의 길이만큼 여백이 필요함
 여백을 추가하고, 그 안에서 문서의 바운딩을 인식. 
 회전한 이미지는 여백을 제외하고 바운딩
 바운딩 기준으로 몇도 회전했느지 에측
 이후 원본으로 바로 새우기

 or

 글자박스를 인식 글 박스를 정면으로 회전
 모든 글 박스를 인식하고 글박스를 정면으로 회전.
 그 후 글 익신

 글 인식에는 글의 외곡, 회전, 기울기 등을 학습 해야 함. (한 영 숫자 기호)
 글의 외곡을 복구하는 방법 필요

---

21/10/31

원근법 이미지
https://opencv-python.readthedocs.io/en/latest/doc/10.imageTransformation/imageTransformation.html

아이디어 노트

접혀진 종이 글씨 또는 접혀진 꼮지점을 인식 - 원근법을 인식해 비율에 따라 복구(정해진 크기가 있음)

각 부분별로 원근법을 통해 복구된 이미지들을 붙임 - 하나의 이미지로 합침

이후 글 인식

or 글 박스를 인식 - 원근법 복원을 통해 각 부분 동일 크기로 맞춤











