# Yelp 레스토랑 데이터 수집기

레스토랑 추천 연구에 쓸 데이터를 모으기 위해 만든 Yelp 크롤러입니다. 도시 이름을 넣으면 그 지역 레스토랑의 기본 정보와 범주별 사진을 수집합니다.

## 수집 항목

- **레스토랑 정보**: 이름, 평점, 카테고리, 가격대, 주소 → `restaurant.csv`
- **사진**: 레스토랑별 사진을 범주(음식, 내부 등)별 폴더에 저장

## 동작 방식

1. Selenium으로 Yelp에서 `Restaurants` + 도시 이름 검색
2. 검색 결과 페이지를 끝까지 넘기며 레스토랑 상세 페이지 방문
3. BeautifulSoup으로 상세 정보를 파싱하고, 사진 탭을 범주별로 순회하며 이미지 저장

## 실행

```python
df = []
res_crawler('NewYork', df)
```

- ChromeDriver 경로와 사진 저장 경로를 본인 환경에 맞게 수정해야 합니다.
- Yelp 페이지 구조가 바뀌면 CSS 선택자를 다시 맞춰야 합니다.
- 학술 연구 목적으로 작성했습니다.

## 기술 스택

Python, Selenium, BeautifulSoup, pandas
