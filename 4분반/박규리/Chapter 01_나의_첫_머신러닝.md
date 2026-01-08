# 인공지능
사람처럼 학습하고 추론할 수 있는 지능을 가진 컴퓨터 시스템을 만드는 기술
- 강인공지능
- 약인공지능


# 머신러닝
규칙을 일일이 프로그래밍하지 않아도 자동으로 데이터에서 규칙을 학습하는 알고리즘을 연구하는 분야
## 사이킷런
- 파이썬 머신러닝 라이브러리
- 성능이 검증된 머신러닝 알고리즘들이 포함되어 있음


# 딥러닝
인공 신경망을 기반으로 한 머신러닝 알고리즘
- LeNet-5: 최초의 합성곱 신경망
- 텐서플로: 구글이 오픈소스로 공개한 딥러닝 라이브러리
- 파이토치: 페이스북이 오픈소스로 공개한 딥러닝 라이브러리
---
# 구글 코랩
클라우드 기반의 주피터 노트북 개발환경 (웹브라우저에서 무료로 파이썬 프로그램을 테스트하고 저장할 수 있는 서비스)
- 텍스트 셀
- 코드 셀
- 노트
---
# 마켓과 머신러닝
## 생선 분류 문제
### 도미 데이터 준비하기
```
# 데이터 추가
bream_length = [25.4, 26.3, 26.5, 29.0, 29.0, 29.7, 29.7, 30.0, 30.0, 30.7, 31.0, 31.0, 31.5, 32.0, 32.0, 32.0, 33.0, 33.0, 33.5, 33.5, 34.0, 34.0, 34.5, 35.0, 35.0, 35.0, 35.0, 36.0, 36.0, 37.0, 38.5, 38.5, 39.5, 41.0, 41.0]
bream_weight = [242.0, 290.0, 340.0, 363.0, 430.0, 450.0, 500.0, 390.0, 450.0, 500.0, 475.0, 500.0, 500.0, 340.0, 600.0, 600.0, 700.0, 700.0, 610.0, 650.0, 575.0, 685.0, 620.0, 680.0, 700.0, 725.0, 720.0, 714.0, 850.0, 1000.0, 920.0, 955.0, 925.0, 975.0, 950.0]

# Scatter Plot (산점도) 출력
import matplotlib.pyplot as plt
plt.scatter(bream_length, bream_weight)
plt.xlabel('length')
plt.ylabel('weight')
plt.show()
```

### 빙어 데이터 준비하기
```
# 데이터 추가
smelt_length = [9.8, 10.5, 10.6, 11.0, 11.2, 11.3, 11.8, 11.8, 12.0, 12.2, 12.4, 13.0, 14.3, 15.0]
smelt_weight = [6.7, 7.5, 7.0, 9.7, 9.8, 8.7, 10.0, 9.9, 9.8, 12.2, 13.4, 12.2, 19.7, 19.9]

# Scatter Plot (산점도) 출력
plt.scatter(bream_length, bream_weight)
plt.scatter(smelt_length, smelt_weight)
plt.xlabel('length')
plt.ylabel('weight')
plt.show()
```

### 첫 번째 머신러닝 프로그램
- K-최근접 이웃 모델 사용, 기본값 K=5 세팅
```
# 도미 데이터와 빙어 데이터 합치기
length = bream_length+smelt_length
weight = bream_weight+smelt_weight
fish_data = [[l, w] for l, w in zip(length, weight)]
fish_target = [1]*35 + [0]*14

# 기본값을 적용한 KNN 알고리즘을 사용해 데이터 학습(fit) 및 평가(score)
from sklearn.neighbors import KNeighborsClassifier
kn = KNeighborsClassifier()
kn.fit(fish_data, fish_target)
kn.score(fish_data, fish_target)
```
score = 1 -> 100% 정확도

### 두 번째 머신러닝 프로그램
- K-최근접 이웃 모델 사용, K=49 세팅
```
# K=49를 적용한 KNN 알고리즘을 사용해 데이터 학습(fit) 및 평가(score)
kn49 = KNeighborsClassifier(n_neighbors=49)
kn49.fit(fish_data, fish_target)
kn49.score(fish_data, fish_target)
```
score = 약 0.71
