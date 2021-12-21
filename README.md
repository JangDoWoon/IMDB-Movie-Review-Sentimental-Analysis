# IMDB-Movie-Review-Sentimental-Analysis
딥러닝 이론 및 실습시간의 과제로 positive, negative label이 포함된 50,000개의 영화리뷰를 이용해 감성분석을 진행하였으며, Dataset이 작은 단점을 보안하고 정확도를 올리기 위해 다음과 같은 모델을 적용함.
## LSTM(Long Short Term Memory)
이는 기존의 RNN이 출력과 먼 위치의 정보를 기억할 수 없는 단점을 해결하기 위해 장기와 단기의 기억을 모두 가능하게 설계한 신경망 구조로 주로 시계열 처리나 자연어 처리에 사용됨. 이는 현재 정보를 저장할지 말지 결정하는 Input Gate, 과거의 정보를 버릴지 말지 결정하는 Forget Gate, 과거의 cell state를 새로운 cell state로 업데이트 하는 Update, 어떤 출력값을 출력할지 결정하는 Output Gate로 이루어짐.

![image](https://user-images.githubusercontent.com/67357059/146860672-08f359aa-8dfc-4968-af2c-35000f139fb4.png)

## Word2Vec
이는 word embedding의 방법 중 하나로 비슷한 분포를 가진 단어는 비슷한 의미를 가정하에 embedding을 진행함. 이런 과정을 갖기 때문에 단어들간의 유사성을 표현할 수 있음. 나는 단순히 50,000개의 리뷰로는 단어간의 관계를 충분히 표현할 수 없다고 생각하였고 word embedding을 위해 Word2Vec을 사용함.

## GRU
이는 LSTM과 비슷한 이유로 만들어 졌으며, LSTM을 구성하는 Time-Step의 Cell이 조금 더 간소화한 버전임. GRU는 LSTM과 학습 속도가 빠르다고 알려졌지만, 비슷한 성능을 보인다고함. 다만 데이터 양이 적을때는 매개 변수의 양이 적은 GRU가 더 낫고, 데이터 양이 더 많으면 LSTM이 더 낫다고 알려져있음. 따라서 IMDB는 Dataset이 작아 GRU를 사용하는 것이 더 낫다고 판단함. 모델적인 면에서 LSTM과의 차이는 GRU는 Gate가 2개이며, 이전 상태를 얼마나 반영할지에 대한 Reset Gate와 이전 상태와 현재 상태를 얼마만큼의 비율로 반영할지에 대한 Update Gate로 이루어져 있으며, Output gate가 없는 것이 특징임.

![image](https://user-images.githubusercontent.com/67357059/146861763-f7d10d1c-607f-4481-8e52-75e5c6c88295.png)

## 결과
결과로 LSTM을 사용했을때 정확도가 84%, Word2Vec을 사용했을때 정확도가 86%, 그리고 GRU와 Word2Vec을 동시에 사용했을 때는 정확도가 87%까지 상승했음.
