---
layout: single
title:  "[Probabilistic inequalities] Chernoff bound"
comments: true
tags: [Probabilistic inequality, Concentration inequality, Probability bounds]
toc: true
classes: wide
last_modified_at: "2022-03-25 02:19:00 +0900"
---

# Intro
chernoff bound는markov and chebyshev inequality([이전 글]({{ site.baseurl }}{% link _posts/2022-03-18-markov_chebyshev.md %}))와 마찬가지로, tail bound에 대해 말한다. 다른 점은 chenorff bound의 경우 MGF(moment generating function)을 사용한다는 것이다[^1].

# Chernoff bound

$$
\begin{aligned}
& \Bbb P \left( X \geq a \right) \leq e^{-ta} M_{X} \left( t \right), \qquad \text{for all $t > 0$},  \\
& \Bbb P \left( X \leq a \right) \leq e^{-ta} M_{X} \left( t \right), \qquad \text{for all $t < 0$},
\end{aligned} \\
$$

chernoff bound는 markov's inequality([이전 글]({{ site.baseurl }}{% link _posts/2022-03-18-markov_chebyshev.md %}))를 활용해 유도할 수 있으며, 유도 과정은 다음과 같다.

$$
\begin{aligned}
\Bbb P \left( X \geq a \right) = & \Bbb P \left( e^{tX} \geq e^{ta} \right),
\qquad \text{(for all $t > 0$)} \\
& \leq \frac{ \Bbb E \left[ e^{tX} \right] }{e^{ta}}, \qquad \text{(markov inequality)} \\
& = e^{-ta} M_{X} \left( t \right)
\end{aligned} \\
$$

모든 $$t$$에 대해 성립하므로, 다음과 같이 우변의 하한(또는 최솟값)을 가지도록 하는 $$t$$일 때 tail bound가 가장 타이트 해진다.


$$
\begin{aligned}

\Bbb P \left( X \geq a \right) \leq \inf_{t \geq 0} e^{-ta} M_{X} \left( t \right)

\end{aligned}
$$




# 끝으로
chernoff bound는 부등식에exponential term 이 붙는다. 따라서 markov나 chebyshev inequality 대비하여 tail이 멀수록 bound가 더욱 타이트해진다.
만약 분포에 대한 정보(e.g. PDF, PMF, MGF)를 안다면, markov나 chebyshev보다 좀 더 타이트한 tail bound를 계산할 수 있다.


# 참고 문서
[^1]: [wiki - chernoff bound](https://en.wikipedia.org/wiki/Chernoff_bound)
