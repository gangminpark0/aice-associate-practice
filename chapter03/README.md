# Chapter 3 · 탐색적데이터분석

[교재 코드 실행 영상](https://youtu.be/qJDyqOYYiSM) · [개념 강의](https://youtu.be/PMzYr4vWPBw) · [전체 실습 목록](../README.md)

노트북: [CH03_실습.ipynb](CH03_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 아나콘다·주피터 소개](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=0s)
- [00:12 · 데이터 넣기: Upload와 파일 위치](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=12s)
- [00:47 · 교재 50쪽 · CSV 불러오기](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=47s)
- [01:27 · 교재 52쪽 · 행과 열의 수](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=87s)
- [01:47 · 교재 53쪽 · 자료형과 결측치 개요](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=107s)
- [02:10 · 교재 53쪽 · 기술 통계 요약](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=130s)
- [02:33 · 교재 54–55쪽 · 숫자형 변수 자세히 보기](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=153s)
- [03:22 · 교재 55쪽 · 범주형 변수의 빈도와 종류](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=202s)
- [04:05 · 교재 56쪽 · 열별 결측치 수](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=245s)
- [04:24 · 교재 57쪽 · 범위로 이상치 살펴보기](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=264s)
- [04:48 · 교재 59쪽 · IQR로 이상치 찾기](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=288s)
- [05:40 · 교재 61쪽 · 결측치가 있는 행 삭제](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=340s)
- [06:05 · 교재 61쪽 · 평균으로 결측치 채우기](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=365s)
- [06:24 · 교재 61쪽 · 중앙값과 최빈값으로 채우기](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=384s)
- [07:01 · 교재 62쪽 · 이상치 행 제외하기](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=421s)
- [07:31 · 교재 62쪽 · clip으로 상한 적용](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=451s)
- [08:06 · 교재 63쪽 · 하한·상한과 IQR clip](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=486s)
- [08:43 · 교재 64쪽 · 객실 등급별 생존율](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=523s)
- [09:13 · 교재 65쪽 · 성별 생존율](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=553s)
- [09:34 · 교재 65쪽 · 피벗 테이블](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=574s)
- [10:05 · 교재 67쪽 · 상관계수 행렬](https://www.youtube.com/watch?v=qJDyqOYYiSM&t=605s)

## 실행 안내

# 실습 데이터 넣기

1. 출판사 제공 데이터 폴더의 `Part2 Titanic.csv`를 준비합니다. 
2. 주피터 파일 목록에서 실습 노트북이 있는 폴더를 엽니다.
3. Upload 버튼을 누르고 `Part2 Titanic.csv`를 선택해 업로드합니다.
4. 목록에 노트북과 CSV 파일이 함께 있는지 확인하고 노트북을 엽니다.
5. `pd.read_csv("Part2 Titanic.csv")`로 읽은 뒤 `head()`와 `shape`로 정상 여부를 확인합니다. 이 자료는 891행·12열입니다.

제공한 결과 폴더에는 노트북과 CSV가 함께 들어 있습니다. 다른 컴퓨터에서도 같은 폴더 구조를 유지하세요. 파일을 다른 위치에 두었다면 코드의 파일 경로를 실제 위치로 바꿔야 합니다. 개인 폴더의 절대경로를 그대로 복사하지 말고 실제 파일 위치를 확인하세요.

`Part2 Titanic.csv`는 교재에서 제공받은 원본과 바이트가 같은 복사본입니다. 원본 CSV는 수정하지 않습니다. 62–63쪽 본문의 시속 clip은 일반적인 범위 제한 방법을 설명하는 예제입니다. 실행용 `speed_df`와 값 [5, 80, 320, 450]은 제작 과정에서 추가했으며, 원본 교재의 데이터 값이나 실제 Titanic 열이 아닙니다.

‘여기서 잠깐’ 보조 코드는 이번 제작에서 제외하며, Excel·JSON·SQL 등의 별도 연습 파일도 제공 대상에서 제외했습니다.
