# 야수사냥 정규식

[poe.re/beast](https://poe.re/beast)의 한국어판 — Path of Exile 한국어 클라이언트용 야수사냥(Bestiary) 정규식 생성기.

아인하르의 야수 우리·야수도감 검색창에 붙여넣으면 값비싼 야수만 골라서 표시해 주는 검색 정규식을 만들어 줍니다.

## 원본과 다른 점

- 야수 이름·정규식이 **한국어 클라이언트 기준**입니다. 포획 가능한 전체 야수 220종의 한국어 이름과 충돌하지 않는 최소 고유 부분문자열을 자체 계산했습니다.
- 제작법 설명은 poedb.tw 한국어 페이지의 실제 게임 문구를 사용했습니다.
- poe.re의 코드를 사용하지 않은 독자 구현입니다(원본 저장소에는 라이선스가 없습니다). 시세 데이터만 poe.re의 공개 엔드포인트(economy.poe.re, poe.ninja 기반)를 사용합니다.

## 동작 방식

- `index.html` 하나로 동작하는 정적 페이지입니다. 페이지가 열릴 때 economy.poe.re에서 실시간 시세를 가져오고, 실패하면 저장소에 커밋된 스냅숏(`data/prices.json`)을 사용합니다.
- GitHub Actions(`update-prices.yml`)가 6시간마다 현재 리그명과 시세 스냅숏을 갱신 커밋합니다.

## 데이터 출처

- 원본 도구: [poe.re](https://poe.re) (veiset)
- 시세: poe.ninja (economy.poe.re 경유)
- 야수 한국어 명칭: 한국 서비스 클라이언트 데이터
- 제작법 번역: [poedb.tw](https://poedb.tw/kr/) 참조
