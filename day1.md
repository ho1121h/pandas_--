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