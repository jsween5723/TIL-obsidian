the quick brown fox jumped over the lazy dog

- ngram 처럼 윈도우의 크기 n을 지정한다.
- 윈도우는 현재 대상인 단어 전후로 n개만큼의 단어(문맥)을 대상으로 한다.
- 윈도우 size 1 일 때, (\[the, brown], quick) 처럼 윈도우 대상이 배열에 순차적으로 들어가 pair를 생성한다.

# 입출력
quick을 입력하면 (quick, the), (quick, brown)과 같이 데이터 쌍으로 출력한다.

구성은 다음과 같다. (MLE)
P(target|history) = softmax(score(target, history)) =>
![[스크린샷 2024-03-09 12.26.51.png]]
여기서 log를 활용해 식을 정리한다.

 ![[스크린샷 2024-03-09 12.35.13.png]]
 언어 모델링을 위해 log likelihood로 적당히 정규화된 모델을 구한다.
 log를 씌우는 이유는 분모가 매우 크기 때문에 너무 작은수 는 절삭오류에 취약하기 때문이다.
 log를 씌워 정규화 효과를 기대할 수 있다.

 