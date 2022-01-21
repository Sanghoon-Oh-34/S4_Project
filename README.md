[CodeStates Project] 넷플릭스 데이터 - 콘텐츠 기반 추천 알고리즘 구현
===

![01](https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/01.jpg)

## 개요
* 코드스테이츠 AI 부트캠프에서 진행한 머신러닝을 활용한 추천 시스템 프로젝트입니다.
* 목적: 콘텐츠 기반 추천 시스템 구현
* 데이터셋: 케글(Kaggle) Netflex Movies and TV Shows(2019) 7,787건

## 내용
1. 선정이유  

 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/06.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/07.jpg' width='400px' height='300px'></img>
* 코로나 유행으로 기존 극장 중심 오프라인 관람에서 OTT 기반 관람문화 심화
* 추천 시스템은 개인화 분석을 통한 취향에 맞는 아이템을 추천함으로써 선택의 피로함을 줄여줌
* 영상뿐만 아니라 음악, 쇼핑 등 다양한 분야에서 추천 알고리즘 활용

<br>

2. 추천 시스템(Recommendation System)  
 
 ![09](https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/09.jpg)
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/10.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/11.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/12.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/13.jpg' width='400px' height='300px'></img>
* 협업 기반 필터링은 사용자 정보를 바탕으로 비슷한 사용자 또는 구매이력을 통한 연관성 활용
* 콘텐츠 기반 필터링은 아이템(콘텐츠) 자체 속성을 분석하여 유사한 아이템을 추천
* 그러나 동일한 카테고리의 아이템만 분석함으로써 확장된 카테고리 추천의 한계점 존재

<br>

3. Word2Vec

 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/19.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/20.jpg' width='400px' height='300px'></img>
* 텍스트를 벡터화하여 비슷한 단어끼리 가까운 좌표에 위치함으로써 단어 간 유사도 측정
* Google News300 임베딩 모델 활용

<br>

4. 모델 구현  

 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/21.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/22.jpg' width='400px' height='300px'></img>
* 장르, 영화설명(시놉시스) 토큰화 진행 후 Word2Vec 모델을 통해 유사도 계산
* 영화명 입력 시 알고리즘을 통해 추천 영화 10개 유사도 높은 순으로 출력

<br>

5. 회고  
 
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/24.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project03/blob/main/2.%20Slides/25.jpg' width='400px' height='300px'></img>
* 개인화 추천이 대세 트렌드이긴 하지만, 비슷한 컨텐츠에 잦은 실증을 유발할 가능성이 있음
* 영화 카테고리뿐만 아니라 관련된 음악, 도서, 굿즈 등 크로스 추천 알고리즘 구현을 고민해보자.
