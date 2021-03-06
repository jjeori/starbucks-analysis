### **패스트 캠퍼스 국비교육_빅데이터 분석 첫걸음 시작하기 FINAL Project**

#### **프로젝트 목적** - 해당 데이터에서 고객들이 이벤트에 대한 응답을 어떻게 하는지 찾고, 고객 프로모션 개선방안에 대한 인사이트 발견하는 것
------------
#### **주어진 데이터 정리**
#### 1. profile table - 설문에 참여한 스타벅스 회원에 대한 관련 정보가 담겨있다.
#### 2. transcript - 이벤트에 참여한 실제 유저들의 응답이 기록되어 있다.
#### 3. portfoilo - 이벤트를 운영했던 내역에 관한 정보가 담겨있다.

------
#### **profile 데이터 정제**
- Nan 값과 해석할 수 없는 id 컬럼을 제거
- age 값은 나이가 다양하게 분산되어 있어서 각 연령대 별로 분류
- became_member_on 값은 Datetime을 활용해 가입년도와 가입월 두 컬럼으로 분류

#### **transcript 데이터 전처리**
- person, value 칼럼은 해석할 수 없는 값으로 판단해서 제거

#### **portfolio 데이터 전처리**
- portfolio 데이터는 10행, 5열로 이루어진 작은 데이터이기에 전처리 과정은 없다

------
### **profile 데이터 시각화 및 Why**
* 성별 비중 - 각각 남성 57.23% 여성 41.34%으로 집계 
<img width="399" alt="스크린샷 2022-06-24 오후 8 49 02" src="https://user-images.githubusercontent.com/99062088/175806298-f81e6b41-536c-4756-89e0-aa25c595f412.png">


* 남성 연령대 기준 설문참여 빈도 - 50대, 60대, 40대 순으로 높게 참여
<img width="510" alt="스크린샷 2022-06-24 오후 8 48 24" src="https://user-images.githubusercontent.com/99062088/175806516-f58d9eb2-76d3-488e-a9dc-20d4c1c69019.png">

* 여성 연령대 기준 설문참여 빈도 - 50대, 60대, 40대 순으로 높게 참여
<img width="509" alt="스크린샷 2022-06-24 오후 8 48 30" src="https://user-images.githubusercontent.com/99062088/175806744-acda19ef-562e-4d5d-8c63-09f24171762b.png">


>**연령대 설문 참여 결과에 대한 Why**

1. '스세권'이라는 말이 있을 정도로 스타벅스를 이용하는 소비자가 많은 것을 알 수 있다. 주요 고객층은 대학생, 직장인인 20대, 30대, 40대로 이루어져 있지만, 정작 설문조사 참여 빈도는 낮다. 그러면 연령대별 참여 빈도 차이는 무엇 때문에 발생하는 것일까?

2. 스타벅스의 주요 연령층은 확실하게 대학생, 직장인인가?

>**나의 생각**
##### 2016년 1000만 건 주문 데이터를 기준으로 20대 30대가 전체 86%를 차지한 것으로 보아 주요 연령층은 대학생과 직장인이다. 그럼에도 불구하고 설문 조사 참여 빈도가 낮은 이유는 설문 조사 목적에서 찾을 수 있지 않을까라는 생각이다.

-------
* 각 연령대에 따른 평균 수입 - 연령대가 높아질 수록 수입이 대체로 증가
<img width="514" alt="스크린샷 2022-06-24 오후 8 48 44" src="https://user-images.githubusercontent.com/99062088/175806781-13407674-4985-467c-9a94-11bac2cb7a17.png">

>**연령대에 따른 평균 수입 결과에 대한 Why**
1. 수입과 참여수의 상관관계가 있을까?

2. 수입이 증가함에 따라 경제적 여유가 있기 때문에 높은 연령대일 수록 참여수가 높지 않을까?

>**나의 생각**

##### 설문 조사 참여 연령대와 수입 증가률을 직관적으로 봤을 때는 연관이 있어보인다. 하지만 단순히 경제적 여유가 있기 때문에 설문 조사 참여 빈도가 높다라고 판단 할 수는 없다. 이를 명확하게 파악하기 위해서는 설문 조사의 목적이 무엇이었는지 알 필요가 있다.
----
* 각 연도 기준 월 별 가입자 수 증감률 - 2013부터 2018년까지 대체로 증가하는데, 2017년 7월 기준으로 대폭적으로 가입자 수가 증가
<img width="505" alt="스크린샷 2022-06-26 오후 5 53 52" src="https://user-images.githubusercontent.com/99062088/175806903-d6aa1632-d20a-4c0a-b97f-fc741f5e9bd0.png">

>**가입자 수 증감률에 대한 Why**
1. 대체로 가입자 수가 증가하고 있지만, 유독 눈에 띄는 것은 2017년 7월 기준으로 대폭 상승하고 있다. 이러한 이유는 무엇일까?

2. 2017년 진행한 캠페인 영향?

3. 2017년 멤버십 혜택 영향?

4. 사회적인 이슈나 스타벅스 운영 방침으로 인한 영향?

>**나의 생각**

##### *캠페인* - 2017년부터 2018년도까지 스타벅스는'일회용컵 없는 날', '서울, 꽃으로 피다'와 같은 환경을 주제로 한 캠페인을 진행했고, 2017년 77만명이 참여한 '우유사랑라떼' 캠페인 또한 진행했다. 캠페인을 통해서 가입자 수는 늘릴 수 있겠지만, 대폭적으로 증가시키는 것은 어느정도 한계가 있다고 생각한다.

##### *혜택* - 네이버 멤버십이나 통신사 멤버십에 가입하는 가장 큰 이유는 바로 '혜택'이었다. 이는 스타벅스 가입자 수 증가에 영향을 가장 많이 줬을 거라 판단해서 2017년 스타벅스 멤버십 혜택을 찾아 본 결과 카드 발급을 받으면 3가지 등급으로 나누어져 있고, 높은 등급일 수록 혜택을 많이 받는 것을 알 수 있다. 하지만, 2016년과 비교해 봤을 때 큰 차이는 없었다.

##### *스타벅스 운영* - 스타벅스의 운영 방침은 '차별성'이다. 타 커피 프랜차이즈와 비교해봤을 때 '콜마이네임'제도를 통해서 고객들이 자발적으로 닉네임을 등록하게 됨으로써 스타벅스 리워드 회원 수가 늘어나는 데 큰 기여를 했고, 이는 진동벨을 사용하는 경쟁사들과 차별성을 둘 수 있었다. 또한, 시즌 한정 음료나 프리퀀시 제도 등은 소비자들에게 매력적인 혜택이자 커피를 마시는 카페 공간이 아닌 즐거운 문화생활을 할 수 있는 특별한 공간으로 여겨지고 있다.


 ##### **현재 주어진 데이터를 통해서는 2017년 7월에 가입자 수가 대폭 증가한 이유를 찾기 힘들다.** 그렇기 때문에 캠페인, 혜택, 스타벅스 운영 이 세가지 중 특정 하나로 인해서 가입자 수가 증가했다고 판단할 수 없다. 나의 의견은 위 세 가지가 시너지를 발휘했기 때문에 꾸준하게 가입자 수가 증가했다고 생각한다.


----
### **transcript 데이터 시각화 및 Why**
* event 빈도 - transaction 45.33%, offer received 24.88%, offer viewed 18.83%, offer completed 10.95% 순으로 집계 
<img width="439" alt="스크린샷 2022-06-24 오후 8 48 50" src="https://user-images.githubusercontent.com/99062088/175806997-c256f61f-d6eb-4592-9bfd-caf4ca7d853d.png">
>**event 빈도에 대한 Why**
1. 이벤트 빈도를 바탕으로 생각해볼 수 있는 개선방안은 무엇이 있을까?


----
### **portfolio 평균**
* 제안유형에 따른 각 칼럼의 평균

<img width="229" alt="스크린샷 2022-06-26 오후 6 00 10" src="https://user-images.githubusercontent.com/99062088/175807092-bff6608e-b63e-4221-bd79-7840b2ad1082.png">


---------------------
## *부족했던 것들*

> ### 1. 그래프 해석
<img width="508" alt="스크린샷 2022-06-26 오후 9 21 32" src="https://user-images.githubusercontent.com/99062088/175813886-4171c5ac-e037-4fdf-becd-0079320f2043.png">

- 각 연도별로 가입자 수를 한눈에 파악하기 위해서 시계열 그래프를 활용하고 해석을 했을 때 "2016년부터 2017년 사이에 대폭 상승하고, 2017년 이후 가입자 수가 하락한다."라고 해석을 했는데 실제 데이터 값을 확인하면 2017년 7월부터 가입자 수가 증가하고, 2017년 이후 가입자 수가 하락하는 것이 아닌, 2018년 데이터는 7월달까지 밖에 없어서 가입자 수가 적게 집계가 되었던 것이다.

- **데이터를 명확하게 파악하고, 이에 적합한 방법으로 시각화를 해야 실수를 줄일 수 있다.**

> ### 2. 데이터 분석과정
- 데이터 분석 목적을 명확하게 하고 어떤 데이터를 추출해야 할 것인지 파악을 하고 분석을 진행해야 하는데, 나는 가지고 있는 데이터들을 무작정 정제하고 시각화를 했다.
- 그래서 목적과는 동떨어진 이야기를 한 느낌이다.

> ### 3. 인사이트 도출
- 데이터를 정제하고 시각화하는 과정보다, 시각화한 데이터를 해석하고 인사이트 도출하는 과정이 더 어렵다는 것을 알게 되었다. 데이터 다루는 기술도 꾸준하게 공부해야겠지만, 여러 그래프들을 보면서 인사이트를 찾는 공부도 필요하다.