---
layout: single
title:  "Probabilistic inequalities"
comments: true
categories: [Probabilistic inequality, Concentration inequality, Probability bounds, Martingale]
toc: false
classes: wide
---

# 시작
stochastic bandit에 대한 논문을 보면, regret bound, upper confidence bound, confidence sets 등의 증명과 계산을 위해 다양한 probabilistic inequality를 활용하는 모습이 자주 보인다[^1]. stochastic bandit의 regret bound에 대해 finite-time 또는 asymptotic behavior를 분석하여, 제시한 모델이 얼마나 효과적인지 말하기 위해서다.

그런데, 동일한 probabilistic inequality를 사용하더라도 표기가 조금 다른 경우가 왕왕있어서 볼 때마다 항상 헷갈린다. 매번 대충 이해하고 넘어가서 그런 것 같다. 자주 사용되는 inequalities에 대한 이해를 높이고자 한번 정리하려고 한다.


# Inequalities 목록
다음 글들에서는 각 inequality의 정의와 특징을 정리하며 stochastic bandit 논문에서의 적용 사례를 예시로 다루려고 한다.
- [Union bound]({{ site.baseurl }}{% link _posts/2022-03-17-union_bound.md %})
- [Markov and Chebyshev inequality]({{ site.baseurl }}{% link _posts/2022-03-18-markov_chebyshev.md %})
- Chernoff bounds
- Triangle inequality
- Cauchy-Schwarz inequality
- Jensen's inequality
- Azma's inequality
- Hoeffding's inequality
- Bernstein inequality


# 참고 문서
[^1]: [Improved Algorithms for Linear Stochastic Bandits. Abbasi-Yadkori (2011)](https://sites.ualberta.ca/~szepesva/papers/linear-bandits-NeurIPS2011.pdf)

