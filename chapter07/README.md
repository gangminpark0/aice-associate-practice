# Chapter 7 · 회귀

[교재 코드 실행 영상](https://youtu.be/Z2jS-Y1GS7I) · [개념 강의](https://youtu.be/YhUPMKZHEYg) · [전체 실습 목록](../README.md)

노트북: [CH07_실습.ipynb](CH07_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 136쪽 · 시작 안내](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=0s)
- [00:10 · 교재 138–139쪽 · 데이터 파일 업로드](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=10s)
- [00:32 · 교재 139쪽 · 훈련·테스트 데이터 분할](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=32s)
- [01:37 · 교재 140쪽 · 선형 회귀 학습](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=97s)
- [02:16 · 교재 141쪽 · 선형 회귀 예측과 비교](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=136s)
- [02:55 · 교재 143쪽 · 결정 트리 회귀](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=175s)
- [03:55 · 교재 145쪽 · 랜덤 포레스트 회귀](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=235s)
- [04:50 · 교재 147–148쪽 · KNN 회귀와 표준화](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=290s)
- [06:01 · 교재 150쪽 · XGBoost와 원-핫 인코딩](https://www.youtube.com/watch?v=Z2jS-Y1GS7I&t=361s)

## 실행 안내

# CHAPTER 07 회귀 실습 자료

1. 압축을 풀어 CH07_실습.ipynb와 Part4 Chapter7 Insurance.csv를 같은 폴더에 둡니다.
2. 아나콘다의 Jupyter Notebook에서 노트북을 엽니다.
3. 새 커널에서 위에서부터 순서대로 실행합니다. Ctrl+Enter는 현재 셀 실행, Shift+Enter는 실행 후 다음 셀로 이동입니다.

CSV는 교재 제공 원본으로 1338행·7열이며 결측치가 없습니다. 직접 따라 입력하려면 Jupyter 파일 목록에서 Upload로 이 CSV를 노트북과 같은 폴더에 올립니다. 다른 폴더를 이용할 때는 pd.read_csv의 경로를 본인의 저장 위치에 맞춰 바꾸세요. 파일 이름의 공백도 그대로 사용합니다.

처음 세 셀은 데이터 분할 → 선형 회귀 학습 → 예측으로 연결됩니다. 네 번째 이후는 CSV를 다시 읽어 각 모델을 준비합니다. 같은 변수 이름에 새 값이 대입되므로 위에서 아래로 실행하세요.

KNN은 훈련 자료에 fit_transform, 테스트 자료에는 transform만 적용합니다. XGBoost는 성별·흡연 여부·지역도 인코딩하여 사용하므로 앞 모델과 입력 특징의 수가 다릅니다. 일부 출력값만으로 모델의 전체 성능을 단정하지 않습니다.

교재 본문 코드 7개, 설명 주석 47개를 원문 문구·순서대로 포함했습니다. 코드 오른쪽 주석도 보존했습니다. PDF 인쇄 줄바꿈으로 나뉜 random_state와 함수 호출 줄만 연결했으며, 설명 주석 사이에는 읽기 편하도록 빈 줄을 넣었습니다. 알고리즘·인수·숫자는 교재와 같습니다. ‘여기서 잠깐’의 별도 코드는 포함하지 않습니다.

필요 패키지: pandas, scikit-learn, xgboost. 설치된 아나콘다의 scikit-learn 1.6.1, xgboost 3.0.1에서 모든 셀을 검증했습니다. 실행 결과도 노트북에 저장되어 있습니다. 예상 결과를 코드 주석으로 덧붙이지 않았습니다.
