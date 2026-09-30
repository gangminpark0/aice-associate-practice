# AICE Associate · 교재 코드 실습

『2026 에듀윌 AI능력시험 AICE ASSOCIATE 한권끝장』을 바탕으로 한 **Chapter 1–12 실습 노트북과 데이터**입니다. 유튜브의 각 장 코드 실행 영상과 함께 활용하세요.

[교재 안내](https://www.yes24.com/product/goods/189505874) · [유튜브 재생목록](https://www.youtube.com/playlist?list=PLVI9aV5nvJnc)

## 시작하기

1. 위쪽 **Code → Download ZIP**을 눌러 전체 자료를 내려받고 압축을 풉니다.
2. Anaconda에서 Jupyter Notebook을 열고 원하는 `chapter01`–`chapter12` 폴더로 이동합니다.
3. `CH번호_실습.ipynb`를 열고 새 커널에서 위에서 아래로 셀을 실행합니다. `Shift+Enter`는 실행 후 다음 셀로 이동합니다.
4. 데이터가 있는 장에서는 **CSV와 노트북을 같은 폴더**에 둡니다. 파일 이름의 공백과 대소문자도 그대로 유지합니다.

각 장 폴더에는 데이터 준비, 실행 순서, 교재와 실행 환경의 차이를 설명한 README가 있습니다. 노트북에는 실제 실행 결과도 저장되어 있습니다.

## 장별 실습 코드와 영상

| 장 | 주제 | 실습 코드·데이터 | 개념 강의 | 코드 실행 영상 |
|---|---|---|---|---|
| 1 | 분석환경구성 | [chapter01](chapter01/) | [보기](https://youtu.be/FOe6xIDE2T0) | [보기](https://youtu.be/eZMt9Xx9qBY) |
| 2 | 데이터이해 | [chapter02](chapter02/) | [보기](https://youtu.be/GTtuBaDAl6s) | [보기](https://youtu.be/7kmDCFuOmdU) |
| 3 | 탐색적데이터분석 | [chapter03](chapter03/) | [보기](https://youtu.be/PMzYr4vWPBw) | [보기](https://youtu.be/qJDyqOYYiSM) |
| 4 | 데이터시각화 | [chapter04](chapter04/) | [보기](https://youtu.be/BncYR4-SFlo) | [보기](https://youtu.be/OcyB5_roUhg) |
| 5 | 전처리기법 | [chapter05](chapter05/) | [보기](https://youtu.be/uxjUarCBC4M) | [보기](https://youtu.be/0RRssFMR28Y) |
| 6 | 정규화및표준화 | [chapter06](chapter06/) | [보기](https://youtu.be/RxORL2QFJSo) | [보기](https://youtu.be/1R3FoQRIrJE) |
| 7 | 회귀 | [chapter07](chapter07/) | [보기](https://youtu.be/YhUPMKZHEYg) | [보기](https://youtu.be/Z2jS-Y1GS7I) |
| 8 | 분류 | [chapter08](chapter08/) | [보기](https://youtu.be/6ZbWHO-8a60) | [보기](https://youtu.be/uy-ePNGbWls) |
| 9 | 비지도학습 | [chapter09](chapter09/) | [보기](https://youtu.be/DFJWsCFkF6A) | [보기](https://youtu.be/ytEfEmr4CQ0) |
| 10 | 딥러닝 | [chapter10](chapter10/) | [보기](https://youtu.be/99PunZRveH8) | [보기](https://youtu.be/GGy_C7kZQsQ) |
| 11 | 성능평가 | [chapter11](chapter11/) | [보기](https://youtu.be/dTCo65QwqFQ) | [보기](https://youtu.be/uKMaKSrNF_w) |
| 12 | 모델튜닝및결과해석 | [chapter12](chapter12/) | [보기](https://youtu.be/hg7ky0PRS4c) | [보기](https://youtu.be/L1YOtGbBUtQ) |

## 실행 환경

검증 환경은 Anaconda의 Python 3.13.5입니다. 패키지 버전은 [requirements.txt](requirements.txt)에 기록했습니다. 이미 준비된 아나콘다 환경은 각 장의 실행 안내에 나오는 패키지가 있는지 확인하면 됩니다. 새 환경을 구성할 때는 해당 Python 환경에서 다음과 같이 설치할 수 있습니다.

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

신경망 학습 결과와 그래프의 일부 표시 형태는 실행 환경·난수에 따라 달라질 수 있습니다. Chapter 4의 한글 글꼴 설정은 Windows 맑은 고딕용이며, 다른 운영체제에서는 해당 장의 안내대로 바꿉니다.

## 교재 코드와 자료 구성

- 영상에 사용한 최종 승인 노트북과 CSV를 그대로 수록했습니다. 교재의 설명 주석과 코드 옆 주석을 보존합니다.
- 교재 본문 실습을 대상으로 하며, ‘여기서 잠깐’의 별도 코드는 제외했습니다.
- 실행을 위한 보완 사항은 해당 장의 README에 명시했습니다. 예: Chapter 3의 일반적인 범위 제한 예제용 데이터, Chapter 6의 열 이름 변경, Chapter 9의 군집 라벨 복원.
- 각 장의 README에는 교재 페이지에 대응하는 유튜브 바로가기가 있습니다.
- CSV는 교재와 함께 제공된 실습 데이터입니다. 교재 PDF·영상·나레이션 제작 파일은 포함하지 않습니다.
