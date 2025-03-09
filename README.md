<h1 style="text-align: center;">🎅🏻 선물 배송 경로 최적화 경진대회: 산타와 루돌프의 워라벨 사수작전</h1>
<hr>
<img src="https://github.com/donghyun0518/dacon-cvrp-optimization/blob/main/santa_certificate.pdf" alt="Project Cover" style="width: 1000px; border: 1px solid #c9d1d9; border-radius: 8px;">
<p style="text-align: center;">
    <a href="https://github.com/donghyun0518/dacon-cvrp-optimization/blob/main/%EC%84%A0%EB%AC%BC_%EB%B0%B0%EC%86%A1_%EA%B2%BD%EB%A1%9C_%EC%B5%9C%EC%A0%81%ED%99%94_%EA%B2%BD%EC%A7%84%EB%8C%80%ED%9A%8C.pdf" target="_blank">
        <img src="https://github.com/donghyun0518/dacon-cvrp-optimization/blob/main/%EC%82%B0%ED%83%80%ED%91%9C%EC%A7%80.png" alt="Project Cover" style="width: 1000px; border: 1px solid #c9d1d9; border-radius: 8px;">
    </a>
</p>

[[프로젝트 발표 자료](https://github.com/donghyun0518/dacon-cvrp-optimization/blob/main/%EC%84%A0%EB%AC%BC_%EB%B0%B0%EC%86%A1_%EA%B2%BD%EB%A1%9C_%EC%B5%9C%EC%A0%81%ED%99%94_%EA%B2%BD%EC%A7%84%EB%8C%80%ED%9A%8C.pdf)]

## 🔍 프로젝트 개요
- **목적** : 한 번에 운반할 수 있는 선물의 개수가 제한되어 있는 효율적인 경로 찾기
- **주제** : 산타의 선물 배송을 위한 경로 최적화 알고리즘 개발
- **기간** : 2024.12.03 ~ 2025.01.31 (약 2달간)
- **팀 구성** : 5인
- **성과** : Private 7th (상위 3%)
- [**데이콘 결과 제출 게시글**](https://dacon.io/competitions/official/236437/codeshare/12186?page=1&dtype=recent)

## ⚙️ 주요 수행 과정
**1. **문제 정의(제약 조건)****
   - 출발점(DEPOT)인 좌표(0,0)에서 출발해 다시 출발점(DEPOT)으로 이동, 배송 해야할 75개 마을의 위치는 0< X,Y <= 100(km) 범위 내
   - 루돌프가 이그는 산타의 썰매는 최대 25개의 선물만 운반
   - 한 마을에는 어린이들에게 배송할 선물을 한 번에 모두 배송
   - 산타와 루돌프는 지점과 지점 사이를 가장 짧은 직선 경로로 이동

**2. **데이터 수집****
   - 데이터 출처 : DACON 제공

**3. 경로 최적화 방법**
 - LKH-3 기반 초기 경로 도출 -> 4-OPT 기반 경로 최적화 -> 최적화 경로 출력
 - **LKH-3**
    - LKH-3 알고리즘은 기존 LKH 알고리즘을 확장한 버전으로, 약 40가지의 다양한 TSP 변형 문제를 해결가능.
    - LKH-3는 문제들을 제약 조건이 있는 TSP로 변환하여 해결하며, K-opt 방법을 사용하여 해공간을 탐색.
    - [다운로드 링크](http://webhotel4.ruc.dk/~keld/research/LKH-3)
    - 제약 조건을 만족하도록 문제 유형을 "CVRP"로 지정, INITIAL_TOUR_ALGORITHM(초기해 생성 알고리즘) 또한 "CVRP"로 지정하여 문제 해결
    - 결과 : 2174.199896169461 (km)
 - **4-opt**
   - 경로 최적화(TSP)에서 사용되는 휴리스틱 기법으로, 경로를 개선하기 위해 4개의 엣지(edge)를 동시에 제거하고 새로운 방식으로 연결하여 총 경로 거리를 줄이는 알고리즘
   - 결과 : 2173.5891486451383 (km)

**4. 최종 경로 시각화**
<img src="https://github.com/donghyun0518/dacon-cvrp-optimization/blob/main/%EC%B5%9C%EC%A2%85%EA%B2%BD%EB%A1%9C%EC%8B%9C%EA%B0%81%ED%99%94.png" alt="Project Cover" style="width: 1000px; border: 1px solid #c9d1d9; border-radius: 8px;">
## 🧑🏻‍💻환경
- Python
- VScode

