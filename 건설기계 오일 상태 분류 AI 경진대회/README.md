# 🤗두번째 대회!!🤗
# 이번 대회는 분류하는 지식증류라는 새로운 기법이 들어갔다.
https://dacon.io/competitions/official/236013/leaderboard

## 분석 과정
- 대회를 시작할 때 딥러닝 모델링을 하다가 어떤 사람이 머신러닝 모델로도 지식증류를 비슷하게 할 수 있다고 말씀을 해주셔서 해봤다. 딥러닝으로 모델링을 할 때 점수가 생각보다 잘 나왔고, 딥러닝뿐만 아니라 GradientBoostingRegressor, DecisionTreeRegressor, LogisticRegression 등 여러 모델을 사용해보았다.

- 딥러닝
딥러닝에서는 손실함수(Relu, PRelu 등)와 옵티마이져(Adam,AdamW, RAdam 등)를 변경해보았고, 신경망 층을 늘려보기 하였다. 그래서 Relu와 AdamW를 사용하였을 때 점수가 제일 높았다. 이후 어떤걸 시도해봐야할지 모르겠어서 머신러닝으로 도전해보았다.

- 머신러닝
머신러닝은 처음에 train피처에서의 1의 확률값을 test의 정답값으로 활용하는 방법이다. 그래서 분류와 회귀 둘다 써야한다.
평가지표를는 f1-macro와 mae를 하였다. rmse를 사용했었는데 rmse보다 mae가 좀 더 robust하기 때문에 mae를 사용하였다.
내 계획은 여러 머신러닝 모델을 만들어서 soft voting해볼려 하였다. 그러나 생각보다 점수가 안나왔다. 나중에 대화 마감 10일 전쯤에 다양하게 실험을 해보다가 threshold의 수치가 중요하다는 것을 깨달았다. threshold값을 0.2로 주었을 때 점수가 가장 잘 나왔고, catboost와 XGB, LGBM을 hard voting과 soft voting을 해봤고, 그 과정에서 hard voting이 점수가 제일 잘나왔다.

## 지식 증류 정리
- 지식증류라는 단어를 처음들어봐서 이에 대해 이해보려고, 많은 자료를 찾아보았다. 내가 이해한 바로 지식증류란 sigmoid 레이어를 거쳐서 나온 확률값의 분포를 soft하게 만들어 내는 과정으로 T값을 이용하여 값이 높아질 경우 soft하게 낮아지면 hard하게 만들어내는 과정이다. 즉, 큰 모델(T)을 학습을 시킨 후 작은 모델(S)을 다음과 같은 손실함수를 통해 학습시키는 과정이이라 볼 수 있다.

## 마무리
- 이번 대회를 하면서 90번 넘도록 제출하였다. 하루 하루 다양한 모델에 대해 공부를 해볼 수 있어서 재밌었던 것 같고, 다양한 실험을 할 수 있어서 재밌었다. 
- 이번 대회를 하면서 아쉬웠던 것은 혼자 대회를 진행하다보니 내가 세운 가설에 대해 물어볼 팀원들이 없었던 것이 아쉬웠고, EDA부터 모델링까지 모든 것을 혼자하다보니 시간과 힘이 많이 들었던 것 같다. 그러나 혼자함으로 인해서 실력이 많이 늘었고, 어떠한 정보를 물어볼 사람이 없기 때문에 오히려 많은 정보를 찾아볼 수 있었던 것 같다.

## 다음 계획
- 이번 대회를 하면서 딥러닝에 대한 지식이 많이 부족하다는 생각이 들었다. 딥러닝에 대해 더 공부를 하고 다음 대회는 딥러닝을 활용하여 참여해볼 계획이다!

