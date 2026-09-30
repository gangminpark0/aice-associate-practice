# Chapter 12 · 모델튜닝및결과해석

[교재 코드 실행 영상](https://youtu.be/L1YOtGbBUtQ) · [개념 강의](https://youtu.be/hg7ky0PRS4c) · [전체 실습 목록](../README.md)

노트북: [CH12_실습.ipynb](CH12_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 224쪽 · 시작 안내](https://www.youtube.com/watch?v=L1YOtGbBUtQ&t=0s)
- [00:13 · 교재 226–227쪽 · 데이터 파일 업로드](https://www.youtube.com/watch?v=L1YOtGbBUtQ&t=13s)
- [00:39 · 교재 226–227쪽 · GridSearchCV 전체 조합 탐색](https://www.youtube.com/watch?v=L1YOtGbBUtQ&t=39s)
- [02:38 · 교재 228–229쪽 · RandomizedSearchCV 무작위 탐색](https://www.youtube.com/watch?v=L1YOtGbBUtQ&t=158s)
- [04:14 · 교재 231–232쪽 · 콜백으로 학습 중단과 최적 모델 저장](https://www.youtube.com/watch?v=L1YOtGbBUtQ&t=254s)
- [06:28 · 교재 233–234쪽 · 손실·정확도 학습 곡선](https://www.youtube.com/watch?v=L1YOtGbBUtQ&t=388s)

## 실행 안내

# CH12 모델 튜닝 및 결과 해석 실습 안내

교재 인쇄 226–234쪽의 본문 실습 네 개입니다. 설명 주석과 인라인 주석 64개를 보존했습니다. 인쇄 폭 때문에 나뉜 주석은 문구를 유지해 연결했습니다.

## 준비와 실행 순서

ZIP을 풀고 노트북과 다음 두 CSV를 같은 폴더에 둡니다. Jupyter의 Upload로 파일을 올려도 됩니다.

- `Part4 Chapter8 Wine Quality.csv` — 와인 1143행·12열. 처음 두 탐색 실습.
- `Part4 Chapter7 Insurance.csv` — 의료비 자료 1338행·7열. 콜백 학습 실습.

다른 폴더라면 `pd.read_csv()`에 자신의 경로를 넣으세요. 노트북은 첫 셀부터 순서대로 실행합니다. 2번은 1번의 데이터 분할을, 4번은 3번의 `history`를 사용합니다.

1번은 36개 후보에 5폴드, 2번은 30개 후보에 5폴드 교차 검증을 하므로 시간이 걸릴 수 있습니다. `n_jobs=-1`은 사용 가능한 모든 CPU 코어를 쓰는 교재 설정입니다. 기다리는 동안 같은 셀을 반복 실행하지 마세요.

## 결과를 읽을 때

첫 두 실습은 `quality` 점수 자체를 클래스로 예측합니다. 검수 환경에서 GridSearchCV의 교차 검증 점수는 0.6476, RandomizedSearchCV는 0.6323, 두 테스트 정확도는 0.69로 교재와 같았습니다. 교차 검증 점수와 별도의 테스트 정확도를 구분합니다.

3번은 의료비 금액을 예측하는 회귀가 아니라 흡연 여부인 `smoker_yes`를 예측하는 분류입니다. 원문처럼 X에서 이 정답 열만 제외하므로 `charges`도 입력 특징에 포함됩니다.

`EarlyStopping`은 검증 손실이 다섯 에포크 동안 개선되지 않으면 중단하고 최적 가중치를 복원합니다. `ModelCheckpoint`는 검증 손실이 개선될 때마다 `best_smoker_model.keras`를 노트북 폴더에 저장합니다. 같은 이름의 모델 파일은 학습 시 갱신됩니다. 셀을 다시 실행하면 모델을 다시 학습하므로 종료 시점과 수치가 달라질 수 있습니다.

4번은 학습 기록의 손실과 정확도를 그립니다. 두 그래프의 훈련·검증 곡선을 함께 비교하세요. 콜백을 사용했다고 항상 좋은 성능이 보장되는 것은 아닙니다.

검수 환경은 Anaconda Python 3.13.5, scikit-learn 1.6.1, TensorFlow 2.20.0, Keras 3.13.2입니다. 현재 Keras가 안내하는 `input_shape` 작성 권고는 실행 오류가 아닙니다. 영상에서는 그 특정 알림만 숨겨 교재 코드를 그대로 보여 주었습니다. 학습 설정과 알고리즘은 바꾸지 않았습니다. 일반 환경에서 해당 권고가 표시될 수 있습니다.

