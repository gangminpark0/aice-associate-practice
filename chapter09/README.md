# Chapter 9 · 비지도학습

[교재 코드 실행 영상](https://youtu.be/ytEfEmr4CQ0) · [개념 강의](https://youtu.be/DFJWsCFkF6A) · [전체 실습 목록](../README.md)

노트북: [CH09_실습.ipynb](CH09_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 171쪽 · 시작 안내](https://www.youtube.com/watch?v=ytEfEmr4CQ0&t=0s)
- [00:11 · 교재 173쪽 · 데이터 파일 업로드](https://www.youtube.com/watch?v=ytEfEmr4CQ0&t=11s)
- [00:34 · 교재 173쪽 · K-Means 군집화](https://www.youtube.com/watch?v=ytEfEmr4CQ0&t=34s)
- [01:41 · 교재 174–175쪽 · K-Means 군집 시각화](https://www.youtube.com/watch?v=ytEfEmr4CQ0&t=101s)
- [02:32 · 교재 176–177쪽 · PCA 차원 축소](https://www.youtube.com/watch?v=ytEfEmr4CQ0&t=152s)
- [03:37 · 교재 177–178쪽 · PCA 결과 시각화](https://www.youtube.com/watch?v=ytEfEmr4CQ0&t=217s)
- [04:31 · 교재 179쪽 · DBSCAN 군집화](https://www.youtube.com/watch?v=ytEfEmr4CQ0&t=271s)
- [05:37 · 교재 180쪽 · DBSCAN 군집 시각화](https://www.youtube.com/watch?v=ytEfEmr4CQ0&t=337s)

## 실행 안내

# CHAPTER 09 비지도학습 실습 자료

압축을 풀고 CH09_실습.ipynb와 Part4 Chapter9 Mall Customers.csv를 같은 폴더에 두세요. Anaconda Jupyter Notebook에서 새 커널로 위에서 아래로 실행합니다. 직접 따라 입력할 때는 파일 목록의 Upload로 CSV를 올립니다. 다른 폴더라면 pd.read_csv에 본인의 저장 경로를 지정하세요.

교재 171–181쪽의 본문 코드 6개입니다. 설명 주석 29개는 문구·순서·인라인 위치를 보존했습니다. 예상 실행 결과를 주석으로 덧붙이지 않았습니다. ‘여기서 잠깐’의 별도 코드는 제외했습니다. 문자열 안의 인쇄 줄바꿈만 복원했으며 함수 호출 안의 정상 줄바꿈은 유지했습니다.

교재 연결 오류 보완: 176쪽에서 CSV를 다시 읽으면 df의 cluster 열이 없어집니다. 네 번째 실습 맨 앞의 df['cluster'] = kmeans.labels_ 한 줄은 177쪽 시각화를 실행하기 위해 추가한 보완 코드입니다. 첫 실습의 KMeans 라벨을 같은 고객 순서에 복원합니다. 나머지 교재 코드와 주석은 그대로입니다.

176쪽 주석의 Mall_Customers.csv라는 이름은 원문대로 보존했고 실제 코드와 제공 파일인 Part4 Chapter9 Mall Customers.csv를 사용합니다. 데이터는 200행·5열, 결측치 0개입니다. 성별 열 이름은 실제 CSV에서 Genre이며 교재 결과의 Gender와 다르지만 이번 입력 피처에 포함되지 않습니다. 원본 데이터는 수정하지 않았습니다.

실행 순서: K-Means 군집화 → 군집 시각화 → PCA 차원 축소 → 기존 군집 라벨 복원 및 PCA 시각화 → DBSCAN 군집화 → DBSCAN 시각화. 첫 셀의 라이브러리와 모델 객체를 뒤 셀에서 사용하므로 같은 노트북에서 순서대로 실행하세요.

K-Means 첫 다섯 라벨은 4·2·4·2·4입니다. PCA 첫 좌표는 (-0.615720, -1.763481)입니다. DBSCAN은 0번 군집 157명, 1번 군집 35명, 노이즈(-1) 8명입니다. PCA는 새 군집을 만드는 방법이 아니며, DBSCAN의 노이즈도 원본에서 삭제되는 것은 아닙니다.

필요 패키지: pandas, scikit-learn, seaborn, matplotlib. 검증 환경은 scikit-learn 1.6.1입니다. Windows MKL의 작은 KMeans 작업 경고를 피하기 위해 촬영 서버와 사전 검사 모두 OMP_NUM_THREADS=1을 적용했습니다. 코드와 실제 실행 결과는 노트북에 저장되어 있습니다.
