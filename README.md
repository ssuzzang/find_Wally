# project4
![image](https://user-images.githubusercontent.com/97435321/192409663-720f2706-d170-4f5f-91c9-ae2e2a8afbb7.png)

---
- 소개 및 목차

![image](https://user-images.githubusercontent.com/97435321/192409747-ee5c6b04-cb56-4d8e-94fc-52f642cacb4d.png)
1. 데이터 구성
  불러오기, 변환, 전처리
2. 모델 구축 및 학습
  CNN 인코더 디코더
3. 월리를 찾아라
  평가
  
![image](https://user-images.githubusercontent.com/97435321/192409943-eb4cbb3b-4996-4c5d-b002-465006dd14b3.png)

- 데이터 선정 이유 : 인공지능에 대해 누구나 친숙하게 다가가고 관심을 가질 수 있도록 하기위해 ‘월리를 찾아서’ 라는 우리에게 친숙한 이미지를 바탕으로 하였습니다.

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7a8024d9-0aad-45d7-b700-e5ca1fd59b71/Untitled.png)

1. Dateset Load(데이터 불러오기)
2. Preview(이미지 확인)
3. Date Generate(데이터 생성)
4. Date EDA

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8e9627e2-5dd0-49ca-8747-673be652857d/Untitled.png)

- 데이터를 확인해 보면 원본 이미지가 있고, 그 이미지에 대한 라벨 이미지, 월리를 그롭한 이미지, 그 이미지에 대한 라벨 이미지 총 4가지로 각각 구성되어 있습니다.

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/54e82ae0-363a-4824-90e4-306c37ed48a2/Untitled.png)

- 데이터의 양이 적어 학습 및 훈련에 부족하여 랜덤으로 크롭하여 데이터를 증식하였습니다..

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/09d99ba7-be5a-4f01-9dd9-448fcd23ea58/Untitled.png)

- 랜덤으로 크롭한 이미지 데이터를 테스트한 결과 화면입니다. 이미지와 라벨이미지 둘다 정상적으로 출력되어 있습니다.

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/af406559-6309-4529-adfe-c5aff61a0059/Untitled.png)

- 월리 포함 유무에 따른 데이터입니다. 1로 표시된 부분이 월리가 포함된 이미지 데이터인데, 월리가 없는 데이터와는 차이가 너무 크기 때문에 학습이 제대로 진행되지 않을 수 있습니다.
- 이 문제에 대해 효과적으로 학습 시키기 위해 데이터에 가중치를 두어 학습 비율을 맞추어 진행 하였습니다.

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c006fa86-57d1-48e3-b8cd-433dac4bce68/Untitled.png)

- 모델 학습 결과 입니다. 총 1000번의 학습을 하였으며, 500번이 넘어가면서 학습의 정확도는 거의 균등하게 나타나는걸로 확인 됩니다.

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d9bea3e7-bb60-431d-838b-df4680ecc0cc/Untitled.png)

- 진행 방법은 원하는 이미지를 균등한 싸이즈로 자른 후 첫번째 판넬에 저장된 이미지를 출력하면 오른쪽의 이미지 처럼 나타납니다.
- 생성된 판넬에 모델을 적용시켜 월리의 유무를 찾아야 합니다.

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d2b26f4b-d270-4c62-91a1-5d68c29fbe6a/Untitled.png)

- 학습된 모델로 예측을 해본 결과 화면 입니다.
- 한부분만 노락색으로 값이 다르게 표시되는데, 이 부분(99.87%)이 월리가 있는 부분입니다.

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5ac3ab1b-4b77-4965-95dc-26cdf28cffa6/Untitled.png)

- 월리가 있는 부분에 박스를 씌어 표시해주기 위해 마스크 값을 확인

---

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5ad616bc-406c-4f08-a554-36d168d381b8/Untitled.png)

- 테스트 이미지에 결과 이미지를 오버레이 하여 월리에게 박스를 씌워줍니다.

---

테스트 1

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e2ad8cda-3c7c-41c1-a147-ded3f8d71eac/Untitled.png)

- 새로운 이미지로 월리를 찾아보기

---

테스트 2

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a465e869-c9e4-4ca7-ac6e-b1c6a58d5e46/Untitled.png)

- 새로운 이미지로 월리를 찾아보기

---
