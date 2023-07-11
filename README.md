# ReviewSentimentAnalysis
2022 하계학부연구생(URP) <네이버 플레이스 별점리뷰 예측 모델 개발 및 활용>

## 💻 프로젝트 소개
<네이버 플레이스 별점리뷰 예측 모델 개발 및 활용>
- 21년 10월 부로 사라진 네이버 플레이스 별점 리뷰를 기반으로, 별점이 매겨져 있지 않은 최근 리뷰들의 별점 예측
- 별점 리뷰 크롤러 개발 및 KcELECTRA 등을 활용한 모델링 진행
- 네이버 플레이스 별점 리뷰의 재도입 제언

개발 기간: 22.06.07 ~ 22.07.15

 
## 💁‍♀️ 팀 구성 
- [성균관대학교 데이터사이언스융합전공] 김보현, 김민, 김선호, 김은지
  
## 🔍 분석 흐름 및 내용
1. 연구 배경 (설문조사)
![image](https://github.com/bohyunee/ReviewSentimentAnalysis/assets/93997717/dd4ce519-c1a3-40f5-89c3-5868d562d477)

3. 크롤러 개발 및 데이터 수집
  - 전국 약 1200개의 식당을 대상으로 식당별 이름, 영업정보, 별점, 리뷰 개수 등의 정보를 추출
  - 각 음식점의 고유한코드 번호를 활용해 식당별 URL을 자동으로 생성
  - 최신순으로 정렬된 리뷰 텍스트를 크롤링 진행
  - 전체 리뷰 222,092개, 별점 있는 리뷰 139,644개를 추출
3. 데이터 전처리
  - 0.5 이상 5 이하의 별점을 0~9 10개의 클래스로 라벨링 
  - 4:1 비율로 train & test split
  - 클래스 불균형을 확인하여 train data는 3.5점을 기준으로 이진분류 진행
![image](https://github.com/bohyunee/ReviewSentimentAnalysis/assets/93997717/1543d43d-2c46-45cb-a711-8b9e5c442b65)
4. 예측 모델 선정 (KcELECTRA, KoBART, KcBERT, RoBERTa 중 정확도가 가장 높았던 KoBART 선정)
![image](https://github.com/bohyunee/ReviewSentimentAnalysis/assets/93997717/bd745d7d-9232-4b58-a979-a71a1bc55900)
5. 리뷰 예측 진행
6. 예측 결과 분석 (임의의 식당 3곳 기반)

## 🍽 분석 결과
#### 예측 모델 적용
- 기존에 노출되던 평균 별점과는 상이한 점수를 기록한 식당 有
- 평균 별점이 갱신되지 않아, 음식점에 대한 정보 일부가 소비자에게 제공되지 못하고 있음
![image](https://github.com/bohyunee/ReviewSentimentAnalysis/assets/93997717/ba2e5fd6-d228-4caa-824a-3bb43f5fb077)

