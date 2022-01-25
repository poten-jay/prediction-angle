# Project 6-2
---
## Goal

<  git config --global core.autocrlf true  >

 - 문서 이미지의 주요값 인식

    1) 딥러닝 네트워크를 활용하여 문서 이미지 회전 각도를 예측하는 모델 학습

       (합성 데이터 11,948 활용 - train, validation 나눠 활용)

       (학습시 이미지를 실제 test 데이터와 분포를 유사하게 맞추는게 중요)

       (학습데이터 추가적 합성 허용)

       (val : 99% , test 95%)

   2) 문서를 정방향으로 맞추기 위한 각도 (0~360)
      - 해당 각도로 회전된 문서

       학습시 회전 시켜서 학습해야함. (pdf)

       Easy ? 문서 자체 왜곡 없는  
       hard ? 왜곡 (구겨지거나 접힌 이미지)

       imgaug, albumentation 라이브러리 사용

       이미지를 구기거나 찌그려 뜨리는 부분을 만들어서 학습해도 됨.


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

21/10/28

https://ichi.pro/ko/opencvleul-sayonghayeo-tegseuteu-imijileul-jadong-eulo-giulgi-bojeong-ttogbalo-haneun-bangbeob-176759562404831

opencv 통한 회전각 예측 - 가능
[ project_3_/기울기 보정.ipynb ]

25도 기울인 사진 => 24.883 도 예측

글 블러 - 흑백 - 줄글 인식 - 묶음 박스처리
 -> 가장 큰 사각형 인식 
 -> 수평 맞춤
(-45 ~ 45 도 사이)

=> OCR 기능 강화 및 0, 90, 180, 270 도 회전 (4번 추가) => 정방향 가능

=> 딥러닝 없이 가능..

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

접혀진 종이 글씨 또는 접혀진 지점을 인식 - 원근법을 인식해 비율에 따라 복구(정해진 크기가 있음)

각 부분별로 원근법을 통해 복구된 이미지들을 붙임 - 하나의 이미지로 합침

이후 글 인식

or 글 박스를 인식 - 원근법 복원을 통해 각 부분 동일 크기로 맞춤

---

21/11/01


이미지 리사이징, 이동, 회전, 원근  
https://blog.naver.com/samsjang/220504966397

테서렉트 사용 이미지 각도 예측  
https://ichi.pro/ko/ocreul-wihan-hoejeon-jeonghwagdo-choejeoghwa-68678004591838

이미지 회전 각도 예측  
https://d4nst.github.io/2017/01/12/image-orientation/


이미지 회전 깃 헙  
https://github.com/d4nst/RotNet


---

21/11/02

이미지 테두리 저장, 회전, 바운딩 박스 처리

---

21/11/03

이미지 테두리 저장, 회전 완료

바운딩 박스 및 라벨리 설정해야함


이미지 축소  
https://qzqz.tistory.com/653


---

21/11/04

이미지 학습에 관해 (cnn, rcnn, fast cnn 등)  
https://velog.io/@qksekf/%EB%94%A5%EB%9F%AC%EB%8B%9D-%EC%A0%81%EC%9A%A9-Segmentation-Object-Recognition

Rbox-CNN Rotated Bounding Box 논문 리뷰  
https://junha1125.tistory.com/21

이미지 기하학적 변형  
https://opencv-python.readthedocs.io/en/latest/doc/10.imageTransformation/imageTransformation.html

라벨링 git   (lableImg)  
https://github.com/tzutalin/labelImg

 - 설치 : pip install labelImg
 - 실행 : labelImg


---

21/11/10

이미지 배경 추가 후 1도마다 300장씩 추가 = > Wall time: 2h 24s

이미지 회전 (annotation 과 함께) => Wall time: 2h 30m 24s

이미지 학습시 :
   - 왜곡 (접힘, 휨, 구겨짐 등)
   - 그림자 (책은 안쪽, 손 or 폰 그림자, 그라데이션 그림자)
   - 밝기, 노이즈 등

---

21/11/11

이미지 배경 추가 후 1도마다 150장씩 추가 = > Wall time: 1h 56s

이미지 회전 (annotation 과 함께) => Wall time: 1h 20min 25s

xml 값 가져오기  
https://lee-mandu.tistory.com/519?category=838684

---

21/11/13

xml 수정 코드 완

 - 모든 이미지 resize 추가 코드 알아보기...

 - 기본 이미지들로 모델 생성하기

 ---

21/11/16

이미지 회전 - 바운딩 박스 - 크롭

df_train : 17분
df_test : 34 초

train -> train_angle : 3시간
train_angle -> train_angle_ro : 3시간

val -> val_angle : 10분
val_angle -> val_angle_ro : 10분

df_train : 17분 (108,000 개)
df_val : 34초 (7200 개)

train_angle_ro , val_angle_ro 폴더 내 png, xml 파일 하나의 폴더로 통합하기
train : 18 분
val : 1 분

폴더를 만들고 박스에 맞춰 이미지 resize 후 폴더에 저장
train :  28000개 28분 /
val :  분

학습 - 에폭 50
10시간 30분


모델 학습 학습

---
