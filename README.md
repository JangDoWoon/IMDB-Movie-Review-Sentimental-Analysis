# IMDB-Movie-Review-Sentimental-Analysis
딥러닝 이론 및 실습시간의 과제로 positive, negative label이 포함된 50,000개의 영화리뷰를 이용해 감성분석을 진행하였으며, 정확도를 올리기 위해 다음과 같은 모델을 적용함.
## LSTM(Long Short Term Memory)
이는 기존의 RNN이 출력과 먼 위치의 정보를 기억할 수 없는 단점을 해결하기 위해 장기와 단기의 기억을 모두 가능하게 설계한 신경망 구조로 주로 시계열 처리나 자연어 처리에 사용됨. 이는 현재 정보를 저장할지 말지 결정하는 Input Gate, 과거의 정보를 버릴지 말지 결정하는 Forget Gate, 과거의 cell state를 새로운 cell state로 업데이트 하는 Update, 어떤 출력값을 출력할지 결정하는 Output Gate로 이루어짐.

![image](https://user-images.githubusercontent.com/67357059/146860672-08f359aa-8dfc-4968-af2c-35000f139fb4.png)

## Word2Vec
