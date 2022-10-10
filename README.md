# project4
![image](https://user-images.githubusercontent.com/97435321/192409663-720f2706-d170-4f5f-91c9-ae2e2a8afbb7.png)
Date : 2022.5.19~2022.5.24

Tags : `keras`  `tensorlow`  `lables`  `skimage` `generator`

---
- 소개 및 목차

![image](https://user-images.githubusercontent.com/97435321/192409747-ee5c6b04-cb56-4d8e-94fc-52f642cacb4d.png)
1. 데이터 구성
  불러오기, 변환, 전처리
2. 모델 구축 및 학습
  CNN 인코더 디코더
3. 월리를 찾아라
  평가
  
---

![image](https://user-images.githubusercontent.com/97435321/192409943-eb4cbb3b-4996-4c5d-b002-465006dd14b3.png)

- 데이터 선정 이유 : 인공지능에 대해 누구나 친숙하게 다가가고 관심을 가질 수 있도록 하기위해 ‘월리를 찾아서’ 라는 우리에게 친숙한 이미지를 바탕으로 하였습니다.

---

![image](https://user-images.githubusercontent.com/97435321/192410237-37895e22-840c-4b9f-931c-c3bb2b7e79de.png)

1. Dateset Load(데이터 불러오기)
2. Preview(이미지 확인)
3. Date Generate(데이터 생성)
4. Date EDA

---

![image](https://user-images.githubusercontent.com/97435321/192410283-b4225ef0-8347-4221-bdec-515b3db04dcc.png)

- 데이터를 확인해 보면 원본 이미지가 있고, 그 이미지에 대한 라벨 이미지, 월리를 그롭한 이미지, 그 이미지에 대한 라벨 이미지 총 4가지로 각각 구성되어 있습니다.

---

![image](https://user-images.githubusercontent.com/97435321/192410308-83097f04-40a2-42e5-8c50-fcfde7f9c53a.png)

- 데이터의 양이 적어 학습 및 훈련에 부족하여 랜덤으로 크롭하여 데이터를 증식하였습니다..

---

![image](https://user-images.githubusercontent.com/97435321/192410340-014fd70e-c733-4035-bc5c-d71d32af38d7.png)

- 랜덤으로 크롭한 이미지 데이터를 테스트한 결과 화면입니다. 이미지와 라벨이미지 둘다 정상적으로 출력되어 있습니다.

---

![image](https://user-images.githubusercontent.com/97435321/192410383-8e717466-39e7-492f-95e7-8bfdddb21602.png)

- 월리 포함 유무에 따른 데이터입니다. 1로 표시된 부분이 월리가 포함된 이미지 데이터인데, 월리가 없는 데이터와는 차이가 너무 크기 때문에 학습이 제대로 진행되지 않을 수 있습니다.
- 이 문제에 대해 효과적으로 학습 시키기 위해 데이터에 가중치를 두어 학습 비율을 맞추어 진행 하였습니다.

---

![image](https://user-images.githubusercontent.com/97435321/192410412-42d0a2b5-8061-4c3f-be2c-8d34767d598d.png)

- 모델 학습 결과 입니다. 총 1000번의 학습을 하였으며, 500번이 넘어가면서 학습의 정확도는 거의 균등하게 나타나는걸로 확인 됩니다.

---

![image](https://user-images.githubusercontent.com/97435321/192410436-2954615b-2378-4227-84b2-33f5323bad4a.png)


- 진행 방법은 원하는 이미지를 균등한 싸이즈로 자른 후 첫번째 판넬에 저장된 이미지를 출력하면 오른쪽의 이미지 처럼 나타납니다.
- 생성된 판넬에 모델을 적용시켜 월리의 유무를 찾아야 합니다.

---

![image](https://user-images.githubusercontent.com/97435321/192410465-d302195e-ba95-4976-b3e2-09d1b2deec11.png)

- 학습된 모델로 예측을 해본 결과 화면 입니다.
- 한부분만 노락색으로 값이 다르게 표시되는데, 이 부분(99.87%)이 월리가 있는 부분입니다.

---

![image](https://user-images.githubusercontent.com/97435321/192410485-29df18a7-5854-44f6-962a-87437f815db9.png)

- 월리가 있는 부분에 박스를 씌어 표시해주기 위해 마스크 값을 확인

---

![image](https://user-images.githubusercontent.com/97435321/192410498-a395db69-8852-4b6b-86d2-4e5530f401f9.png)

- 테스트 이미지에 결과 이미지를 오버레이 하여 월리에게 박스를 씌워줍니다.

---

테스트 1

![image](https://user-images.githubusercontent.com/97435321/192410516-7532ecd6-e878-4261-b54b-3414f8e97d32.png)

- 새로운 이미지로 월리를 찾아보기

---

테스트 2

![image](https://user-images.githubusercontent.com/97435321/192410585-ac5ff988-1adf-4950-8cb8-07566f7f3a41.png)

- 새로운 이미지로 월리를 찾아보기


---

- 느낀점
    - 이 프로젝트를 하면서 월리를 얼마나 잘 찾을지 너무 궁금해 하면서 프로젝트를 시작하게되었습니다.
    - 월리를 찾는 것이 사진마다 조금씩 정확도도 다르고 정답률이 100퍼가 아니라서 조금 아쉽습니다.
    - 정확도를 올리는 방법에 대해서 수정할 필요가 있을 것 같습니다.

