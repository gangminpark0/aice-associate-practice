# Chapter 11 · 성능평가

[교재 코드 실행 영상](https://youtu.be/uKMaKSrNF_w) · [개념 강의](https://youtu.be/dTCo65QwqFQ) · [전체 실습 목록](../README.md)

노트북: [CH11_실습.ipynb](CH11_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 210쪽 · 시작 안내](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=0s)
- [00:14 · 교재 210–211쪽 · 데이터 파일 업로드](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=14s)
- [00:40 · 교재 210–211쪽 · 분류 모델 준비와 정확도](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=40s)
- [02:07 · 교재 212쪽 · 오차 행렬](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=127s)
- [02:47 · 교재 214쪽 · 정밀도·재현율·F1 스코어](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=167s)
- [03:36 · 교재 215–216쪽 · 회귀 모델 준비와 MAE](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=216s)
- [04:50 · 교재 217쪽 · MSE와 RMSE](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=290s)
- [05:40 · 교재 218쪽 · R² 결정 계수](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=340s)
- [06:18 · 교재 218–220쪽 · 오차 행렬 히트맵](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=378s)
- [07:52 · 교재 221쪽 · ROC 곡선과 AUC](https://www.youtube.com/watch?v=uKMaKSrNF_w&t=472s)

## 실행 안내

# CH11 성능 평가 방법 실습 안내

교재 인쇄 210–223쪽의 본문 코드 여덟 개를 순서대로 실행합니다. 코드와 설명 주석 61개를 교재와 동일하게 포함했습니다. 인쇄 줄바꿈만 코드에 맞게 연결했으며 R² 표기를 보존했습니다.

## 데이터 준비

ZIP을 풀고 아래 파일을 노트북과 같은 폴더에 둡니다. Jupyter의 Upload로 두 CSV를 올려도 됩니다.

- `CH11_실습.ipynb`
- `Part4 Chapter8 Wine Quality.csv` — 와인 분류, 1143행·12열.
- `Part4 Chapter7 Insurance.csv` — 의료비 회귀, 1338행·7열.

다른 폴더에 보관했다면 `pd.read_csv()`의 경로를 자신의 위치로 수정하세요. 파일명과 띄어쓰기를 그대로 유지합니다.

## 실행 순서와 확인

첫 셀부터 차례로 실행합니다. 1–3번은 같은 와인 예측, 4–6번은 같은 의료비 예측을 사용합니다. 7번에서 와인 분류 모델을 다시 만들고 8번에서 그 모델의 확률을 사용합니다. 중간 셀만 먼저 실행하면 변수 또는 모델이 다른 상태일 수 있습니다.

검수 환경에서 정확도 0.9083, 정밀도 0.6522, 재현율 0.5357, F1 0.5882, MAE 9181.31, RMSE 11454.32, R² 0.1549, AUC 0.9010을 확인했습니다. 새 커널에서 여덟 실습을 정상 실행했고 교재와 수치가 일치합니다.

오차 행렬은 행이 실제값, 열이 예측값이며 이 데이터에서는 0·1 순서입니다. 히트맵의 색은 각 칸의 개수를 나타냅니다. ROC에는 확정 라벨 대신 좋은 와인일 확률을 전달합니다. R²는 분류 정확도가 아니며 일반적으로 음수가 될 수도 있습니다.

검수 환경: Anaconda Python 3.13.5, pandas 2.2.3, scikit-learn 1.6.1, matplotlib 3.10.0, seaborn 0.13.2. 그래프 표시 모양은 환경에 따라 조금 달라질 수 있습니다.
