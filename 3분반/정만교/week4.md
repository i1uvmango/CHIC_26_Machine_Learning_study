# week4 차원축소

## 키워드
```
- 다중공선성, 차원의 저주
- 전진선택, 후진소거, Stepwise
- PCA, MDS
```


## 군집화 - Unsupervised Learning(비지도학습)
* 정답 label y 가 없을때 사용
* feature 에 따라서 그래프에서 data 들이 뭉치는 현상
* 중심점 : cluster 의 각 점부터 중심점을 구함 (x좌표 /n , y좌표/n)
* Sum of Distance : cluster 의 중심점으로 부터 각점까지의 거리
    * sum of distance 가 최소가 되는게 좋은 군집화
### 차원축소
* 변수가 너무 많으면 `가시화` 가 어려움 &rarr; 차원 축소를 통해 가시화 용이하게 만듦
* PCA, MDS

