# 602377113 장민서
# [5월 4일]

## 상자 그림
- 상자그림 : 사분위수를 시각화하여 그래프의 형태로 나타낸 것
- 단일변수 수치형 자료를 파악하는데 사용됨
```
dist <- cars[,2]
boxplot(dist, main='자동차 제동거리')
```
## obxplot.stats() 함수
- 데이터의 전반적인 분포를 이해하는 데는 도움이 되지만, 구체적으로 최솟값, 최댓값, 중앙값 등이 정확히 얼마인지 계산할 때 사용

## 그룹이 있는 상자그림
```
boxplot(Petal.Length~Species,
          data=iris,             
          main='품종별 꽃잎의 길이',       
          col=c('green','yellow','blue'))
```

## 산점도
- 다중변수 데이터에서 두 변수에 포함된 값들을 2차원 그래프상에 점으로 표현항 분포를 관찰할 수 있도록 하는 도구
- 관측값들의 분포를 보고 두 변수 사이의 관련성을 확인하는데 사용

## 다중 산점도
- plot()함수는 변수가 2개 이상인 데이터에 대해 변수를 2개씩 짝지어 산점도 작성
- 대각선을 기준으로 오른쪽 위의 산점돌과 왼쪽 아래의 산점도들이 대칭을 이룸
- 여러 변수들 간의 추세를 한눈에 파악 가능

## 탐색적 데이터 분석

### 데이터 분석 절차
- 1단계 : 문제 정의 및 계획
- 2단계 : 데이터 수집
- 3단계 : 데이터 정제 및 전처리
- 4단계 : 데이터 탐색
- 5단계 : 데이터 분석
- 6단계 : 결과 보고

### 1. 문제 정의 및 계획
- 무제가 명확해야 그 문제를 해결하기 위해 어떤 데이터를 수집해야 하는지 알 수 있고, 어떤 분석 기법을 적용해야 하는지도 계획할 수 있음
- 문제 정의를 바탕으로 데이터 분석에 대한 계획 수립

### 2. 데이터 수집
- 문제를 해결하기 위해 필요한 데이터가 무엇인지 파악

### 3. 데이터 정제 및 전처리
- 수집된 데이터를 분석 가능한 형태로 정돈

### 4. 데이터 탐색
- 가벼운 데이터 분석
- 분석을 위해 정돈된 데이터 자체를 이해하고 파악
- 비교적 쉬운 통계 기법을 적용

### 5. 데이터 분석
- 파악한 정보를 이용하여 심화된 분석을 수행
- 통계 분석, 군집 분석, 분류 분석, 주성분 분석, 시계열 분석 등 고급 분석 기법들 사용

### 6. 결과 보고
- 데이터 분석과 해석이 마무리 되면 내용을 정리하여 보고서 형태로 작성
- 처음에 했던 문제 정의에 대해 문제를 해결하는데 도움이 되는 내용을 요약

# [4월 27일]

## 테이블 생성
- 벡터 변수 생성 및 초기화 후 table(벡터변수) 명령어를 이용

## 막대그래프
```
favorite <- c('Winter', 'Summer', 'Sprring', 'Summer', 'Summer', 'fail', 'fail', 'Summer', 'Spring', 'Summer', 'Summer')
table(favorite)
ds <- table(favorite)
barplot(ds, main = 'Favorite Season', col = c('skyblue', 'azure2', 'gold', 'gray'), xlab='계절', ylab='빈도 수', horiz=TRUE)
```

## 색상 함수
```
colors()
```

## 히스토그램
- 외관상 막대그래프와 비슷한 그래프
- 그룹이 명시적으로 존재하지 않는 수치형 자료의 분포를 시각화할 때 사용
```
head(cars)
dist <- cars[,2]
dist
hist(dist, main='Histogram for 제동거리', xlab='제동거리', ylab='빈도 수', border='blue', col='green', las=2, breaks=5)
```
## 선 그래프
```
month <- 1:12
late <- c(5,7,6,5,4,3,2,1,2,3,12,13)
plot(month, late, main='지각생 통계', type ='1', lty = 1, lwd = 1, xlab='Month', ylab ='Late cnt')
```

# [4월 13일]

## if-else문
```
if(비교조건) {
조건이 참일 때 실행할 명령문
} else {
조건이 거짓일 때 실행할 명령문
}
```

## ifelse문
- if-else문을 서술할 때 조건에 따라 선택할 값이 각각 하나씩이면 ifelse문을 이용
- ifelse 문법
```
ifelse(비교 조건, 조건이 참일 때 선택할 값, 조건이 거짓일 때 선택할 값)
```

## for문
```
for(반복 변수 in 반복 범위) {
반복할 명령문(들)
}
```

## while문
```
while (비교 조건){
반복할 명령문(들)
}
```

## apply() 함수
```
apply(데이터셋, 행/열 방향 지정, 적용 함수)
```
- 반복 작업의 대상이 매트릭스나 데이터프레임의 행이나 열인 경우 이용
- 매트릭스나 데이터프레임에 있는 행들이나 열들이 하나하나 차례로 꺼내어 평균이나 합계 등을 구하는 작업을 수행하고자 할 때 유용

## apply() 함수에서 사용되는 매개변수의 의미
- 데이터셋 : 반복 작업을 적용할 대상인 매트릭스나 데이터프레임 이름을 입력한다
- 행/열 방향 지정 : 행 방향 작업의 경우 1, 열 방향 작업의 경우 2를 지정한다
- 적용 함수 : 반복 작업의 내용을 알려주는 것으로, R 함수이거나 사용자 정의 함수를 지정한다

## which() 함수
- 조건에 맞는 값이 벡터 안에서 몇 번째 위치하고 있는지 알아내는 함수
- which.max() 함수 : 벡터 안에서의 최댓값의 인텍스를 알아내는 함수
- which.min() 함수 : 벡터 안에서의 최솟값의 인텍스를 알아내는 함수

# [3월 23일]

## R 패키지 생성하는 방법
```
install.package("패키지이름")
library(패키지이름")
```

## 변수에 대해 알아야 할 것들
- 하나의 변수에는 하나의 값만 저장 가능
- R에서는 여러 개의 값을 한 곳에 저장 가능하게 해주는 백터(vector) 제공

## 변수명의 작명 규칙
- 첫 글자는 영문자나 마침표(.)로 시작 ex) avg, .total
- 두 번째 글자 부터는 영문자, 숫자, 마침표(.), 밑줄(_)을 사용 가능

## 변수에 저장될 수 있는 값의 종류
- 숫자형 : 정수 / 실수 모두 가능
- 문자형 : "" / ''로 묶어서 사용
- 논리형 : TRUE / FALSE ( T,F로 줄여서 사용 가능 )
- 특수값 : NULL / NA(결측값) / NaN(수학적으로 정의가 불가능한 값) / Inf, -Inf (잘 사용하지 않음)
