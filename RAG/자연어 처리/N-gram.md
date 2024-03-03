N = k+1 번째 올 문자
N이 커질수록 이전에 온 문자들을 k만큼 기억하고 그에 따라 k+1번째에 올 경우를 예측
its water is so transparent that => the 
P(A, B)
/ P(A)
일 때 the를 결과로 추론하는 모델을 7-gram이라고 표현

2-gram 3-gram

대표적으로 Uni-gram, Bi-gram, Tri-gram이 있다.
this is a book
this is a book
this is a car 
uni = \[this], \[is], \[a], \[book]
bi = \[this, is], \[is, a], \[a, book]
tri = \[this, is, a], \[is, a, book]
<s> <s> this is a book </s></s>


구현은 대부분 특정 데이터에서 해당 단어조합이 등장한 횟수를 기반으로
$$
\frac{C(k+1)}{C(k)}
$$
위 처럼 구할 수 있다.

그러나 특정 단어에 대한 정보가 입력된 데이터에 없을 경우 분모나 분자가 0이 될 수 있다.
보완을 위해 [[Char-RNN]]을 주로 사용하게 되었다.
