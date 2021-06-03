## VGGNet

16개 또는 19개 층으로 구성된 모델을 의미한다.(VGG16, VGG19)

cf) AlexNet은 8개 층을 가지고 병렬적 구조로 이루어져있다.

​     ResNet은 152개의 층으로 구성. 

### 구조

Convolution kernel 사이즈를 고정하고 

( ∵ 네트워크 깊이(depth)의 영향을 확인하고자 설계된 네트워크라서)

Convolution의 개수를 늘리는 방식으로 테스트 진행.

Convolution layer는 kernel 사이즈 3x3, padding 사이즈 1로 설정한다. 

(max pooling을 사용해서 이미지를 resize한다. convolution layer를 통해서 하는게 아님)



### 특징

3x3 convolution 연산을 여러번 하는 것은 여러번의 비선형 처리를 해주는 것이므로, 큰 필터로 한번 연산 했을 때 보다 더 많은 비선형성을 가질 수 있다. 

파라미터 수 = 3^2 * 채널개수^2



### 단점

VGGNet은 간단한 구조를 가졌지만, fully connected layer가 3개가 있고, 풀링(pooling)을 거친 뒤에는 피쳐맵의 갯수가 2배로 커지면서 필요한 **파라미터가 과도하게 많아졌다.** 파라미터가 많다는 것은 딥러닝의 고질적인 문제인, gradient vanishing, 과적합등의 문제가 발생할 가능성이 크다는 의미이다

출처: https://datascienceschool.net/view-notebook/47c57f9446224af08f13e1f3b00a774e/



https://m.blog.naver.com/laonple/221259295035

https://89douner.tistory.com/61

https://wegonnamakeit.tistory.com/2

https://www.elfarchive.org/2017/11/vggnet.html

https://bskyvision.com/504