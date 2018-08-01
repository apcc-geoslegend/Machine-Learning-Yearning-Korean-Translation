## 27 Techniques for reducing variance

개발되는 학습 알고리즘이 높은 분산치를 보인다면, 다음과 같은 기법들을 시도해 볼 수 있다:

- 더 많은 학습 데이터를 추가하는 것: 가장 간단하면서도 가장 안정적으로 분산의 문제를 해결할 수 있는 방법이다. 하지만, 의미 있을 정도의 더 많은 데이터와 이를 계산하기 위한 비용을 감당할 수 있어야 한다.

- (L2, L1, Dropout) 과 같은 정규화 기법을 사용하는 것: 이 기법들은 분산치을 줄여주지만, 편향치는 증가하게 한다.

- 학습을 조금 일찍 종료 시키는 것 (개발 데이터셋에 기반하여 경사하강법을 일찍 종료): 이 기법은 분산치를 줄여주지만, 편향치는 증가하게 한다. 일찍 학습을 종료하는 것은 정규화 기법과 꽤나 유사한 모습을 보여주고, 몇몇 사람들은 이 또한 정규화 기법에 포함시키기도 한다.

- 입력 Feature의 종류 또는 개수를 줄이기 위하여 Feature를 선정하는 것:  이 기법은 분산이 가지는 문제에 도움을 줄 수 있다. 하지만, 편향치를 증가시키게 될 지도 모른다. 1,000개에서 900개로 Feature의 개수를 아주 약간만 줄이는 것은 편향에 큰 영향을 미치지 않는다. 만약 1,000개에서 100개로 처럼 크게 Feature의 개수를 줄이게 되면, 많은 유용한 feature들을 제외하게 되어서, 결과적으로 편향에 더 큰 영향을 주게 된다. 현대의 딥러닝에서, 충분한 데이터가 존재할때, feature 선정에 대한 어떤 변화가 있었는데, 그것은 가지고 있는 모든 feature를 알고리즘에게 주고 알고리즘이 스스로 어떤 feature가 더 유용한지를 정렬하여 결정하도록 하는 것이다. 하지만, 학습 데이터의 수가 적다면, feature 선택 기법은 매우 유용하게 사용될 수 있을 것이다.

- 뉴런/레이어의 개수등을 조절하여 모델 크기를 줄이는 것: 이 기법은 조심하게 사용되어야 한다. 이 기법은 분산치를 줄여줄 수는 있으나, 편향치를 증가시킬 가능성이 있다. 하지만, 개인적으로 분산 문제를 해결하기 위해서 이 기법의 사용을 추천하고 싶지는 않다. 정규화 기법을 사용하는것이 더 좋은 분류 성능을 가져올 수 있을 것이다. 모델 크기를 줄이는 것의 이점은 계산에 사용되는 비용을 줄일 수 있고, 따라서 모델을 학습시키는 시간을 단축 할 수 있다는 것이다. 모델의 학습 속도를 끌어 올리는게 유용하다고 판단되면, 모델 사이즈를 줄이는 것을 가장 먼저 검토해 보자. 그러나, 만약 목적이 분산치를 줄이는 것인데 계산에 드는 비용에 걱정이 없다면, 정규화 기법을 사용하는 것을 고려해 보자.

다음은 앞선 챕터에서 이야기된 편향을 해결하기 위한 추가적인 두가지 전략이다:

- 에러 분석으로 부터 얻은 통찰력에 기반한 입력 feature를 변경하는 것: 에러를 분석한 내용이 알고리즘의 특정 에러 카테고리를 제거하는데 도움을 주는 추가적인 feature를 생성하는 것에 대하여 어떤 영감을 주었다고 가정해 보자 (더 많은 내용을 다음 챕터에서 다룰 것이다). 이 새로이 정의된 feature는 편향과 분산 모두에게 도움이 될 수도 있다. 이론적으로, 더 많은 feature를 추가하면 분산치가 증가하게 된다; 하지만, 이 경우에는 정규화 방법을 사용해서 분산치 증가를 제거해 나갈 수 있다. 

- 모델의 설계 구조를 변경하여 주어진 문제에 더 적합하도록 만드는 것: 이 기법은 분산과 편향 모두에게 영향을 끼칠 수 있다.
