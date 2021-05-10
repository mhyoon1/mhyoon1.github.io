---
title: 'Matplotlib를 이용한 데이터 시각화'
author: Myung-Hyun Yoon
layout: post
permalink: /matplotlib/
dsq_thread_id:
  - 
categories:
  - AI
---

matplotlib를 이용한 데이터 시각화
Numpy는 파이썬이 계산과학분야에 이용될때 핵심 역할을 하는 라이브러리입니다. Numpy는 고성능의 다차원 배열 객체와 이를 다룰 도구를 제공합니다. 
만약 MATLAB에 익숙한 분이라면 Numpy 학습을 시작하는데 있어 이 튜토리얼이 유용할 것입니다. <!--more-->

# Scatterplot

## x, y, colors, area 설정하기
* colors 는 임의 값을 color 값으로 변환합니다.
* area는 점의 넓이를 나타냅니다. 값이 커지면 당연히 넓이도 커집니다.
```
x = np.random.rand(50)
y = np.random.rand(50)
colors = np.arange(50)
area = x * y * 1000
plt.scatter(x, y, s=area, c=colors)
plt.show()
```

## cmap과 alpha
* cmap에 컬러를 지정하면, 컬러 값을 모두 같게 가져갈 수도 있습니다.
* alpha값은 투명도를 나타내며 0 ~ 1 사이의 값을 지정해 줄 수 있으며, 0에 가까울 수록 투명한 값을 가집니다.
```
np.random.rand(50)
plt.figure(figsize=(12, 6))
plt.subplot(131)
plt.scatter(x, y, s=area, cmap='blue', alpha=0.1)
plt.title('alpha=0.1')
plt.subplot(132)
plt.title('alpha=0.5')
plt.scatter(x, y, s=area, cmap='blue', alpha=0.5)
plt.subplot(133)
plt.title('alpha=1.0')
plt.scatter(x, y, s=area, cmap='blue', alpha=1.0)
plt.show()
```

# 2. Barplot, Barhplot
1개의 canvas 안에 다중 그래프 그리기

## 2-1. 기본 Barplot 그리기
```
x = ['Math', 'Programming', 'Data Science', 'Art', 'English', 'Physics']
y = [66, 80, 60, 50, 80, 10]
plt.bar(x, y, align='center', alpha=0.7, color='red')
plt.xticks(x)
plt.ylabel('Number of Students')
plt.title('Subjects')
plt.show()
```
## 2-2. 기본 Barhplot 그리기
barh 함수에서는 xticks로 설정했던 부분을 yticks로 변경합니다.
```
x = ['Math', 'Programming', 'Data Science', 'Art', 'English', 'Physics']
y = [66, 80, 60, 50, 80, 10]
plt.barh(x, y, align='center', alpha=0.7, color='green')
plt.yticks(x)
plt.xlabel('Number of Students')
plt.title('Subjects')
plt.show()
```
