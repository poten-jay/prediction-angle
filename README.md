# Project 6-2
---
## Goal

<  git config --global core.autocrlf true  >

 - ���� �̹����� �ֿ䰪 �ν�

    1) ������ ��Ʈ��ũ�� Ȱ���Ͽ� ���� �̹��� ȸ�� ������ �����ϴ� �� �н�

       (�ռ� ������ 11,948 Ȱ�� - train, validation ���� Ȱ��)

       (�н��� �̹����� ���� test �����Ϳ� ������ �����ϰ� ���ߴ°� �߿�)

       (�н������� �߰��� �ռ� ���)

       (val : 99% , test 95%)

   2) ������ ���������� ���߱� ���� ���� (0~360)
      - �ش� ������ ȸ���� ����

       �н��� ȸ�� ���Ѽ� �н��ؾ���. (pdf)

       Easy ? ���� ��ü �ְ� ����  
       hard ? �ְ� (�������ų� ���� �̹���)

       imgaug, albumentation ���̺귯�� ���

       �̹����� ����ų� ��׷� �߸��� �κ��� ���� �н��ص� ��.


---
### �۾� ��Ʈ 

---

21/10/26
������ - �ռ� �̹��� 11,948

data ��ũ  
https://drive.google.com/file/d/1Byk5fABsGdYWlSuKzXwieQO_4KP0Uk_t/view?usp=sharing

--- 

21/10/27
������� ��Ī

����1) �̹��� �νķ� ������ ���� CNN ��� �̹��� ȸ�� ���� �˰���

����2) BYOL - �ڰ����� �н� (���� �ڰ����� �н��� �������� �ذ�)
https://yuhodots.github.io/deeplearning/21-04-04/

�������Ʈ

���� ���� �˰���  
https://ichi.pro/ko/opencvleul-sayonghayeo-tegseuteu-imijileul-jadong-eulo-giulgi-bojeong-ttogbalo-haneun-bangbeob-176759562404831

---

21/10/29

[���� ���� �˰���] ����Ʈ �⺻ ����

---

21/10/30

���� ȸ���� �н�  
https://kr.mathworks.com/help/deeplearning/ug/train-a-convolutional-neural-network-for-regression.html


�� ȸ���� ��ǥ  
https://lee-mandu.tistory.com/520?category=838684

ȸ�� ���� ���� �󿵿� ����  
https://blog.nerdfactory.ai/2020/09/10/image-augmentation-for-object-detection.html


https://zephyrnet.com/ko/%EB%94%A5-%EB%9F%AC%EB%8B%9D%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EC%9E%90%EB%8F%99-%ED%9A%8C%EC%A0%84/


���̽� �̹��� ȸ�� ���� ����  
https://ansan-survivor.tistory.com/954


 - ���̵�� ��Ʈ

 �̹��� �߽��� ���� ȸ�� = �밢���� ���̸�ŭ ������ �ʿ���
 ������ �߰��ϰ�, �� �ȿ��� ������ �ٿ���� �ν�. 
 ȸ���� �̹����� ������ �����ϰ� �ٿ��
 �ٿ�� �������� � ȸ���ߴ��� ����
 ���� �������� �ٷ� �����

 or

 ���ڹڽ��� �ν� �� �ڽ��� �������� ȸ��
 ��� �� �ڽ��� �ν��ϰ� �۹ڽ��� �������� ȸ��.
 �� �� �� �ͽ�

 �� �νĿ��� ���� �ܰ�, ȸ��, ���� ���� �н� �ؾ� ��. (�� �� ���� ��ȣ)
 ���� �ܰ��� �����ϴ� ��� �ʿ�

---

21/10/31

���ٹ� �̹���  
https://opencv-python.readthedocs.io/en/latest/doc/10.imageTransformation/imageTransformation.html

���̵�� ��Ʈ

������ ���� �۾� �Ǵ� ������ �������� �ν� - ���ٹ��� �ν��� ������ ���� ����(������ ũ�Ⱑ ����)

�� �κк��� ���ٹ��� ���� ������ �̹������� ���� - �ϳ��� �̹����� ��ħ

���� �� �ν�

or �� �ڽ��� �ν� - ���ٹ� ������ ���� �� �κ� ���� ũ��� ����

---

21/11/01


�̹��� ������¡, �̵�, ȸ��, ����  
https://blog.naver.com/samsjang/220504966397

�׼���Ʈ ��� �̹��� ���� ����  
https://ichi.pro/ko/ocreul-wihan-hoejeon-jeonghwagdo-choejeoghwa-68678004591838

�̹��� ȸ�� ���� ����  
https://d4nst.github.io/2017/01/12/image-orientation/


�̹��� ȸ�� �� ��  
https://github.com/d4nst/RotNet


---

21/11/02

�̹��� �׵θ� ����, ȸ��, �ٿ�� �ڽ� ó��

---

21/11/03

�̹��� �׵θ� ����, ȸ�� �Ϸ�

�ٿ�� �ڽ� �� �󺧸� �����ؾ���


�̹��� ���  
https://qzqz.tistory.com/653


---

21/11/04

�̹��� �н��� ���� (cnn, rcnn, fast cnn ��)  
https://velog.io/@qksekf/%EB%94%A5%EB%9F%AC%EB%8B%9D-%EC%A0%81%EC%9A%A9-Segmentation-Object-Recognition

Rbox-CNN Rotated Bounding Box �� ����  
https://junha1125.tistory.com/21

�̹��� �������� ����  
https://opencv-python.readthedocs.io/en/latest/doc/10.imageTransformation/imageTransformation.html

�󺧸� git   (lableImg)
https://github.com/tzutalin/labelImg

 - ��ġ : pip install labelImg
 - ���� : labelImg


---

21/11/10

�̹��� ��� �߰� �� 1������ 300�徿 �߰� = > Wall time: 2h 24s

�̹��� ȸ�� (annotation �� �Բ�) => Wall time: 2h 30m 24s


�̹��� �н��� :
   - �ְ� (����, ��, ������ ��)
   - �׸��� (å�� ����, �� or �� �׸���, �׶��̼� �׸���)
   - ���, ������ ��


