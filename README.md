 문제 요약 
주어진 데이터 y=w  0 ​  +w  1 ​  x+ϵ (단,  𝜖 ∼ 𝑁 ( 0 , 1 ) ϵ∼N(0,1))를 생성한 후, 손으로 구한 회귀 계수와 경사하강법으로 구한 계수를 비교하시오.
데이터 생성 과정
np.random.seed(42)
n = 100
x = np.random.rand(n) * 10
w0_true, w1_true = 2, 3
epsilon = np.random.normal(0, 1, n)
y = w0_true + w1_true * x + epsilon
방법 (1): 최소제곱법
X = np.vstack([np.ones(n), x]).T
w_ls = np.linalg.inv(X.T @ X) @ X.T @ y
계산된 계수 
w 0≈2.215
w 1≈2.954
결과 비교 및 시각화
![image](https://github.com/user-attachments/assets/fd05db2b-8af1-45ea-a603-436496257faa)
빨간선은 진짜 직선
파란선은 최소제곱법 결과
초록선은 경사하강법 결과
