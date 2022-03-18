---
layout: single
title:  "[Probabilistic inequalities] Markov and Chebyshev inequalities"
comments: true
categories: [Probabilistic inequality, Concentration inequality, Probability bounds]
toc: true
classes: wide
last_modified_at: "2022-03-19 02:19:00 +0900"
---

# Intro
markov inequality와 chebyshev inequality는 random variable의 tail bound를 평균과 분산을 통해 표현한다.

# Markov inequality


$$X$$가 non-negative random variable 이면,

$$
\Bbb P \left( X \geq t \right) \leq \frac{ \Bbb E \left[ X \right] }{ t }, \qquad \text{for any} \ t \gt 0
$$

또는


$$
\Bbb P \left( X \geq k \Bbb E \left[ X \right] \right) \leq \frac{ 1 }{ k }, \qquad \text{for any} \ k \gt 0
$$


markov inequality는 non-negative random variable이 조건이며, 
이를 만족하면 어떠한 분포이던 random variable이 특정 값 $$t$$ 이상일 확률의 upper bound가 $$\Bbb E \left[ X \right] / t$$ 라는 것을 말한다. 
증명은 다음과 같다[^1].

$$
\Bbb E \left[ X \right] \geq t \cdot \Bbb P \left( X \geq t \right) + 0 \cdot \Bbb P \left(X \lt t  \right) =  t \cdot \Bbb P \left( X \right)
$$

또한 임의의 monotonic increasing function $$\varphi$$ 에 대해 다음을 만족한다.

$$
\Bbb P \left( X \geq t \right) \leq \frac{ \Bbb E \left[ \varphi \left( X \right)  \right]}{\varphi \left( t \right)} \qquad  \left( \because \Bbb P \left( X \geq t \right) = \Bbb P \left( \varphi \left( X \right) \geq \varphi \left( t \right) \right) \right)
$$

이러한 성질에 의해, non-negative random variable의 tail bound를 n-th moment로 나타낼 수 있다.

$$
\Bbb P \left( X \geq t \right) \leq \frac{\Bbb E \left( X^n \right)}{t^n}
$$


# Chebyshev inequality

For a random variable $$X$$,

$$
\Bbb P \left( \lvert X - \Bbb E \left[ X \right] \rvert \geq t \right) \leq \frac{ Var \left( X \right)}{t^2}, \qquad \text{for any} \ t \gt 0
$$

또는

$$
\Bbb P \left( \lvert X - \Bbb E \left[ X \right] \rvert \geq t Var \left( X \right) \right) \leq \frac{ 1 }{t^2}, \qquad \text{for any} \ t \gt 0
$$

chebyshev inequality는 평균을 기준으로 tail 부분의 확률이 bounded 되어 있음을 말하며, bounded 된 정도는 분산과 관련있음을 말한다[^2].
수식


# 끝으로
markov 또는 chebyshev와 같은 inequalies는 일반적인 확률 분포에 모두 적용 가능한 inequalities이다. 
따라서, 이를 통해 계산한 확률의 bound는 충분히 타이트하지 않을 수 있다.
예를 들어, chebyshev inequality 를 $$ X \sim N \left( 0, 1 \right) $$ 인 random variable에 적용하면, 

$$
\Bbb P \left( \lvert X \rvert \geq t \right) \leq \frac{1}{t^2}
$$

이다. 여기서, $$t = 2$$ 이면, $$ \Bbb P \left( \lvert X \rvert \geq 2 \right) \leq 0.25$$ 가 된다.
그런데, 정규분포에서 random variable의 값이 $$2\sigma$$ 범위 밖일 확률은 $$0.046 (= 1 - 0.954)$$ 으로, chebyshev inequality 를 통해 구한 값보다 작음을 알 수 있다. 

분포를 모르거나 혹은 분포에 대한 가정없이 일반적인 결론을 얻고자 한다면, 이러한 inequalities 들을 적용해볼 수 있겠다.
한 예로, chebyshev inequality는 weak law of large number 증명에 활용된다[^3].


# 참고 문서
[^1]: [wiki - markov's inequality](https://en.wikipedia.org/wiki/Markov%27s_inequality)
[^2]: [wiki - chebyshev's inequality](https://en.wikipedia.org/wiki/Chebyshev%27s_inequality)
[^3]: [wiki - law of large number](https://en.wikipedia.org/wiki/Law_of_large_numbers#Proof_of_the_weak_law)
