# RunTimeError

> UserWarning: Error detected in MkldnnConvolutionBackward. Traceback of forward call that caused the error:

이 error는 loss를 backward할때 발생한다. 

generator의 optimizer가 step과정을 거치면서 가중치가 변경되어 loss를 backward할때 backpropagation이 진행이 안된다고 한다.

해결법 : zero_grad() 이후 다시 generator로 똑같은 input을 넣어서 이미지를 생성하고 다시 discriminator에 통과시켜주면 된다.
