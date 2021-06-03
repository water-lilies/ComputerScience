## Why Deep Learning

2012년 이후 핫해짐

1. 하드웨어가 좋아져서 
   - GPU로 병렬 처리 가능
   - TPU(Tensor)
2. 인터넷의 발전
3. 알고리즘의 발견
   - 크리티컬한 문제를 해결할 수 있게됨



input --- node layer --- output

​        date represiotation

데이터를 표현하는 층의 개수가 많아서 딥러닝

================================

forword step

데이터가 곱해져서 나온 값과

이를 통해서 loss funtion과 cost function 계산하는 과정



backword step 

cost function값을 낮추기위해 

거꾸로 output에서부터 input까지 미분하는 과정(역전파)

==================================== 이게 epoch 한번







이미지는 연산량이 많아서 일반적인 MLP모델로는 비효율적

그래서 등장한 것이 **CNN**



vertical edge horizontal edge 필터



CNN모델은 필터를 학습 하는 것. convolution



=============================================

RNN

번역에 많이 쓰임(텍스트 분석, 감성 분석, 시계열 분석)



문장의 경우 매트릭스의 길이가 들쭉날쭉 달라서 고정 매트릭스 사용 불가



웨이트값을 공유함 



양방향 RNN (bidirection)



활성함수 <= 비선형성을 주기 위해서



vanishing gradient

곱해주는 연산이 너무 크거나 작으면 학습이 잘 안됨





GRU

타우 연산이랑 tanh 연산이랑 더해줌

과거 데이터를 참고하겠다.



LSTM

update foget output



=========================================