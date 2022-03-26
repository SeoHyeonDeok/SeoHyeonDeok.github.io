---
layout: single
title:  "[Probabilistic inequalities] Union bound"
comments: true
tags: [Probabilistic inequality, Concentration inequality, Probability bounds]
toc: false
classes: wide
last_modified_at: "2022-03-17 16:19:00 +0900"
---

# 시작
union bound[^1]는 하나 이상 events의 union이 발생할 확률은 bounded되어 있다는 것을 말한다.
다른 inequalities 유도에 기본이되는 inequality여서 가장 먼저 정리하고자한다.

union bound는 boole's inequality를 주로 말한다. boole's inequality의 일반적인 형태로는 bonferroni inequalities가 있다.
boole's inequality는 events 발생 확률의 upper bound에 대한 것이고, 
bonferroni inequalities는 upper bound와 lower bound 모두에 대해 기술한다.

이번 글에서는 boole's inequalitty와 bonferroni inequalities를 정리하려고 한다.


# Boole's inequality

$$
\Bbb P \left( \bigcup \limits_{i=1} A_{i} \right) \leq \sum_{i} \Bbb P \left( A_{i} \right)
$$

boole's inequality는 `하나 이상 events의 union이 발생할 확률은 개별 event 발생 확률의 합보다 작거나 같다`라는 것을 말한다.
다르게 말하면, `union of events 확률의 upper bound가 개별 event 발생 확률의 합`이라는 것이다. 
모든 events가 서로 disjoint sets라면 equality가 성립한다. booles' inequality는 measure theory의 subadditivity에 해당한다[^3].


# Bonferroni inequalities
bonferroni inequalities는 union of events가 발생할 확률에 대한 upper bound 와 lower bound를 알려준다.

$$\begin{aligned}
\Bbb P \left( \bigcup \limits_{i=1}^{n} A_{i} \right) & \leq \sum_{i} \Bbb P \left( A_{i} \right); \\  
& \geq \sum_{i} \Bbb P \left( A_{i} \right) - \sum_{i \lt j} \Bbb P \left( A_{i} \cap A_{j} \right); \\
& \leq \sum_{i} \Bbb P \left( A_{i} \right) - \sum_{i \lt j} \Bbb P \left( A_{i} \cap A_{j} \right) + \sum_{i \lt j \lt k} \Bbb P \left( A_{i} \cap A_{j} \cap A_{k} \right); \\ 
& \vdots
\end{aligned}$$

inclusion-exclusion principle[^2]을 떠올려보면, 위 식의 inequality가 당연하게 받아들여진다.
예시로 events가 $$A, B$$ 두가지인 경우를 생각해볼 수 있는데, 두 events에 대해 $$\Bbb P \left( A \cup B \right) = \Bbb P \left( A \right) + \Bbb P \left( B \right) - \Bbb P \left( A \cap B \right)$$ 이므로,
$$ \Bbb P \left(A \cup B \right) \leq \Bbb P \left( A \right) + \Bbb P \left( B \right) $$가 성립하는 것을 알 수 있다.
이는 위 수식의 첫번째 줄에 해당하는 결과이다. 


수식을 조금 다르게 적어보면 다음과 같이 쓸 수 있다. $$n$$은 events 수이고, $$k$$는 $$[1, n]$$ 사이의 임의의 값이다.

$$
\begin{aligned}
& \Bbb P \left( \bigcup \limits_{i=1}^{n} A_i \right) \leq \sum_{j=1}^{k} \left( -1 \right) ^{j-1} S_{j} , \qquad \text{For odd $k$ in 1, ..., n} \\ 
& \Bbb P \left( \bigcup \limits_{i=1}^{n} A_i \right) \geq \sum_{j=1}^{k} \left( -1 \right) ^{j-1} S_{j} , \qquad \text{For odd $k$ in 2, ..., n}
\end{aligned} \\
$$

where 

$$
\begin{aligned}
& S_{1} := \sum_{i=1}^{n} \Bbb P \left( A_{i} \right) \\  
& S_{2} := \sum_{1 \geq i \le j \leq n} \Bbb P \left( A_{i} \cap A_{j} \right) \\
& S_{k} := \sum_{1 \geq i_1 \le ... \le i_k \leq n} \Bbb P \left( A_{i_1} \cap ... \cap A_{i_k} \right)
\end{aligned}
$$

위 식에서 $$k = 1$$인 경우가 boole's inequality에 해당한다.
그리고 $$k = n$$인 경우 등호가 성립하는데,
이는 union of events 발생 확률에 inclusion–exclusion principle[^2]를 적용한 것과 동일한 형태이다.

 
# 참고 문서
[^1]: [wiki - boole's inequality](https://en.wikipedia.org/wiki/Boole%27s_inequality)
[^2]: [wiki - inclusion-exclusion principle](https://en.wikipedia.org/wiki/Inclusion%E2%80%93exclusion_principle)
[^3]: [wiki - measure theory](https://en.wikipedia.org/wiki/Measure_(mathematics)#Measure_of_countable_unions_and_intersections)
