# Chapter 10 · 딥러닝

[교재 코드 실행 영상](https://youtu.be/GGy_C7kZQsQ) · [개념 강의](https://youtu.be/99PunZRveH8) · [전체 실습 목록](../README.md)

노트북: [CH10_실습.ipynb](CH10_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 182쪽 · 시작 안내](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=0s)
- [00:11 · 교재 185쪽 · 데이터 파일 업로드](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=11s)
- [00:36 · 교재 185쪽 · 와인 데이터 준비](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=36s)
- [01:54 · 교재 187쪽 · MLP 모델 구조 설계](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=114s)
- [02:47 · 교재 188쪽 · MLP 학습 방법 설정](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=167s)
- [03:24 · 교재 189쪽 · MLP 학습 실행](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=204s)
- [04:15 · 교재 190쪽 · 이진 분류 예측과 비교](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=255s)
- [05:03 · 교재 192쪽 · DNN과 Dropout 구조](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=303s)
- [06:03 · 교재 193쪽 · DNN 컴파일과 학습](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=363s)
- [06:42 · 교재 195–196쪽 · 다중 분류 딥러닝](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=402s)
- [08:42 · 교재 197–198쪽 · 의료비 회귀 딥러닝](https://www.youtube.com/watch?v=GGy_C7kZQsQ&t=522s)

## 실행 안내

# CHAPTER 10 딥러닝 실습자료

압축을 풀고 CH10_실습.ipynb와 CSV 두 개를 같은 폴더에 두세요. Anaconda Jupyter Notebook에서 새 커널로 위에서 아래로 실행합니다. 직접 입력할 때는 파일 목록의 Upload로 CSV를 올립니다. 다른 폴더라면 pd.read_csv에 자신의 저장 경로를 지정하세요.

- Part4 Chapter8 Wine Quality.csv: 와인 분류용, 1,143행·12열.
- Part4 Chapter7 Insurance.csv: 마지막 의료비 회귀용, 1,338행·7열.

둘 다 교재의 원본 파일이며 결측치가 없습니다. 원본을 수정하지 않았습니다.

교재 182–200쪽의 본문 코드 9개입니다. 코드의 설명 주석 52개는 문구·순서·인라인 위치를 보존했습니다. 예상 실행 결과를 주석으로 덧붙이지 않았습니다. 인쇄로 나뉜 random_state만 복원하고 들여쓰기를 정리했습니다. ‘여기서 잠깐’의 설치 코드는 제외했습니다.

1→5번은 와인 데이터 준비, MLP 설계, 컴파일, 학습, 예측 순서입니다. 6·7번은 같은 데이터로 DNN과 Dropout을 설계하고 학습합니다. 8번은 와인 원본을 다시 읽어 3등급 다중 분류를 진행합니다. 9번은 의료비 데이터와 회귀 모델로 바뀝니다. 같은 변수 이름을 다시 사용하므로 순서대로 실행하세요.

필요 패키지는 pandas, numpy, scikit-learn, tensorflow입니다. 확인한 환경은 TensorFlow 2.20.0, Keras 3.13.2, scikit-learn 1.6.1입니다. Keras가 최신 입력층 작성법을 권하는 input_shape 경고를 표시할 수 있으나 교재 코드는 정상 실행됩니다. 영상용 커널에서는 이 권고와 여러 모델을 순서대로 만든 데 따른 retracing 안내만 걸렀습니다. 예외나 다른 경고는 숨기지 않았습니다. 모델 코드는 교재와 같습니다.

신경망 초기화와 Dropout 등에는 난수가 포함됩니다. random_state=42는 데이터 분할을 고정할 뿐, 학습 수치 전체를 고정하지 않습니다. 교재나 영상과 수치가 조금 달라도 오류를 뜻하지 않습니다. MLP 파라미터 929개, DNN+Dropout 파라미터 3,393개와 각 출력의 형태를 확인하세요.

교재처럼 X_test_scaled와 y_test를 validation_data로 사용합니다. 이 점수를 완전히 별개인 최종 평가 데이터의 성능으로 해석하지 마세요. 처음 다섯 예측의 일치 여부도 전체 정확도와 다릅니다. 회귀 예제에서는 실제 의료비와 차이가 큰 행도 그대로 보여 줍니다.

전체 학습 로그는 노트북에 남겼습니다. 영상에서는 마지막 에포크와 예측표에 초점을 맞춥니다. DNN 구조표는 위쪽 층 구성에서 아래쪽 파라미터 합계로 스크롤해 확인합니다.
