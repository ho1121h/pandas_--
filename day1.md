1. 데이터 전처리
- 데이터 분석 작업 전에 데이터를 분석하기 좋은 형태로 만듬
2. 종류
- 정제: 없는 데이터를 채우고,잡음 제거, 모순성 제거하고 교정
- 통합: 여러 개의 데이터 소스를 통합
- 축소: 샘플링 등을 통해 데이터 볼륨을 줄이거나 분석 대상 속성을 줄임
- 변환: 정규화, 집단화 하는 작업
- 정제 
    - 결측값: 데이터가 비어있는 경우
    - 이상값: 특정 범위를 벗어나는 극단값

---
1. 데이터 결합
    -데이터가 여러개의 테이블에 나뉘어 저장된 경우, 실제 사용해야하는 시점에 데이터를 연결하여 사용해야함
2. 방법
- 두테이블간에 공통으로 존재하는 컬럼을 키로 선정
- join Type을 기준을 데이터를 결합한다
3. 종류
    - inner: 교집합 [pd.merge(df1,df2,how='inner',on='a')]
    - outer:합집합 [pd.merge(df1,df2,how='outer',on='a')]
    - left [pd.merge(df1,df2,how='left',on='a')]
    - right [pd.merge(df1,df2,how='right',on='a')]

---
1. 데이터시각화
- 분석결과를 효과적으로 전달함
- 구체적인 분석에 앞서 데이터 전체에 대한 이해를 할 수 있다.
```py
import matplotlib.pyplot as plt
#원그래프
plt.pie(sizes,labels=labels,colors=colors,autopct='%1.1f%%',startangle=90)
plt.hist(bike_data2.Distance,color='b',bins=1000)#히스토 그램
plt.show()
plt.boxplot(bike_data2.Distance)
plt.show()
plt.plot(bike_data['Distance'].groupby(bike_data['Date_out']).sum())
plt.show()#시간에 따른 데이터의 변화를 선그래프로 표현함
```
2. 탐색적 데이터에 빈번히 활용되는 함수
- value_counts():특정 컬럼 내용을 구성하는 값과 각 값의 빈도
- pivot_table: 데이터를 원하는 기준으로 요약 정리하는 방법
- melt :요약된 테이블을 다시 전 테이블로 만듬

3. 정규분포
- 통계의 이론적 중심에 있는 분포이고 종모양의 비ㅐ칭의 형태로 자연 현상에서 종종발견됨
- 중심극한 정리 : 어떤 모집단에서 표본을 취하고 평균을 구할때, 횟수가 충분히 크면 표본 평균은 정규 분포를 따름
- 히스토그램:정규분포, 중심극한정리를 확인할 때 활용 할 수 있다.
```py
#정규분포이해하기
import matplotlib.pyplot as plt
import numpy as np
random_sample=np.random.normal(loc =10 , scale =2 ,size=1000)
plt.hist(random_sample,bins = 100)
plt.show()#대략 분포의 모양을 알 수있다,
```
- 큐큐 플롯:이론적인 값과 실제 데이터 값을 비교하여 확인할 수 있다.
```py
import pylab
import scipy.stats as stats
norm_sample = np.random.normal(loc = 20 , scale =5, size = 100)#평균 20,표준편차5,데이터 100개
stats.probplot(norm_sample,dist='norm',plot = pylab)
#무작위로 만든 샘플데이터를 정규분포에 근사한 형태가 되도록 만듬
pylab.show()#QQ플롯
```