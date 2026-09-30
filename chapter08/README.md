# Chapter 8 · 분류

[교재 코드 실행 영상](https://youtu.be/uy-ePNGbWls) · [개념 강의](https://youtu.be/6ZbWHO-8a60) · [전체 실습 목록](../README.md)

노트북: [CH08_실습.ipynb](CH08_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 154쪽 · 시작 안내](https://www.youtube.com/watch?v=uy-ePNGbWls&t=0s)
- [00:10 · 교재 157쪽 · 데이터 파일 업로드](https://www.youtube.com/watch?v=uy-ePNGbWls&t=10s)
- [00:31 · 교재 157쪽 · 로지스틱 회귀 학습](https://www.youtube.com/watch?v=uy-ePNGbWls&t=31s)
- [01:37 · 교재 158쪽 · 로지스틱 회귀 예측](https://www.youtube.com/watch?v=uy-ePNGbWls&t=97s)
- [02:13 · 교재 159–160쪽 · 결정 트리 분류](https://www.youtube.com/watch?v=uy-ePNGbWls&t=133s)
- [03:14 · 교재 161쪽 · 랜덤 포레스트 분류](https://www.youtube.com/watch?v=uy-ePNGbWls&t=194s)
- [04:09 · 교재 163쪽 · KNN 분류와 표준화](https://www.youtube.com/watch?v=uy-ePNGbWls&t=249s)
- [05:08 · 교재 163쪽 · KNN 예측](https://www.youtube.com/watch?v=uy-ePNGbWls&t=308s)
- [05:41 · 교재 166쪽 · SVM 분류](https://www.youtube.com/watch?v=uy-ePNGbWls&t=341s)
- [06:46 · 교재 167–168쪽 · XGBoost 분류](https://www.youtube.com/watch?v=uy-ePNGbWls&t=406s)
- [07:47 · 교재 169쪽 · 기존 XGBoost 코드](https://www.youtube.com/watch?v=uy-ePNGbWls&t=467s)
- [08:09 · 교재 169쪽 · LightGBM으로 변경](https://www.youtube.com/watch?v=uy-ePNGbWls&t=489s)

## 실행 안내

# CHAPTER 08 분류 실습 자료

압축을 풀고 CH08_실습.ipynb와 Part4 Chapter8 Wine Quality.csv를 같은 폴더에 두세요. Anaconda Jupyter Notebook에서 새 커널로 위에서 아래로 실행합니다. 직접 따라 입력할 때는 파일 목록의 Upload로 CSV를 올립니다. 다른 폴더라면 pd.read_csv에 본인의 저장 경로를 지정하세요.

교재 154–170쪽의 본문 코드 10개를 실습합니다. 설명 주석 54개는 문구·순서·인라인 위치를 그대로 보존했습니다. 예상 실행 결과를 주석으로 덧붙이지 않았습니다. 인쇄 너비로 분리된 random_state와 함수 인자 줄바꿈만 복원했습니다. ‘여기서 잠깐’은 제외했습니다.

157쪽 주석에는 winequality-red.csv라는 이름이 있지만 실제 코드와 제공 파일은 Part4 Chapter8 Wine Quality.csv입니다. 주석을 보존하고 코드의 실제 파일을 사용했습니다. 데이터는 1,143행·12열, 결측치 0개입니다.

1→2번은 로지스틱 회귀 학습→예측, 5→6번은 KNN 학습→예측으로 이어집니다. 나머지 완전한 모델 예제는 데이터를 새로 읽습니다. 같은 변수 이름을 재사용하므로 순서대로 실행합니다. KNN·SVM에서는 훈련 자료에 fit_transform, 테스트 자료에 transform만 적용합니다.

9·10번은 XGBoost와 LightGBM의 라이브러리·모델 생성 두 줄을 비교하는 정상 본문 코드입니다. 모델 객체만 생성하여 출력 표가 없는 것이 정상입니다. 학습된 모델을 만드는 fit까지 수행한 것은 아닙니다.

필요 패키지: pandas, scikit-learn, xgboost, lightgbm. 검증 환경은 scikit-learn 1.6.1, xgboost 3.0.1, lightgbm 4.7.0입니다. 모든 코드와 실행 결과는 실제 촬영 노트북에 저장되었습니다.
