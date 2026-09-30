# Chapter 5 · 전처리기법

[교재 코드 실행 영상](https://youtu.be/0RRssFMR28Y) · [개념 강의](https://youtu.be/uxjUarCBC4M) · [전체 실습 목록](../README.md)

노트북: [CH05_실습.ipynb](CH05_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 100쪽 · 시작 안내](https://www.youtube.com/watch?v=0RRssFMR28Y&t=0s)
- [00:14 · 교재 101쪽 · 데이터 준비](https://www.youtube.com/watch?v=0RRssFMR28Y&t=14s)
- [00:40 · 교재 101쪽 · 데이터 로드와 결측치 확인](https://www.youtube.com/watch?v=0RRssFMR28Y&t=40s)
- [01:25 · 교재 103쪽 · 결측치가 있는 행 제거](https://www.youtube.com/watch?v=0RRssFMR28Y&t=85s)
- [01:52 · 교재 104쪽 · 결측치가 많은 열 제거](https://www.youtube.com/watch?v=0RRssFMR28Y&t=112s)
- [02:19 · 교재 104–105쪽 · 차고 관련 결측치 채우기](https://www.youtube.com/watch?v=0RRssFMR28Y&t=139s)
- [03:21 · 교재 105–106쪽 · 중앙값과 최빈값으로 채우기](https://www.youtube.com/watch?v=0RRssFMR28Y&t=201s)
- [04:16 · 교재 107쪽 · 라벨 인코딩](https://www.youtube.com/watch?v=0RRssFMR28Y&t=256s)
- [05:03 · 교재 108쪽 · 원 핫 인코딩](https://www.youtube.com/watch?v=0RRssFMR28Y&t=303s)
- [05:48 · 교재 110–111쪽 · 열 이름 바꾸기](https://www.youtube.com/watch?v=0RRssFMR28Y&t=348s)
- [06:27 · 교재 111쪽 · 데이터 타입 바꾸기](https://www.youtube.com/watch?v=0RRssFMR28Y&t=387s)
- [07:03 · 교재 112쪽 · 불필요한 Id 열 제거](https://www.youtube.com/watch?v=0RRssFMR28Y&t=423s)
- [07:29 · 교재 113쪽 · X와 y 분리](https://www.youtube.com/watch?v=0RRssFMR28Y&t=449s)
- [08:17 · 교재 114–115쪽 · 병합용 학생·동아리 명단](https://www.youtube.com/watch?v=0RRssFMR28Y&t=497s)
- [09:09 · 교재 116쪽 · 공통 학번으로 inner 병합](https://www.youtube.com/watch?v=0RRssFMR28Y&t=549s)

## 실행 안내

# 전처리 기법 실습 준비

압축파일을 풀고 모든 파일을 같은 폴더에 둡니다. 아나콘다의 Jupyter Notebook에서 CH05_실습.ipynb를 열고 위에서 아래로 실행하세요.

- **Part3 House Price.csv**: 교재 제공 주택 가격 원본 데이터이며 1,460행·81열입니다. 이전 장의 타이타닉 데이터와 다릅니다.
- CSV를 별도로 넣으려면 노트북이 있는 Jupyter 폴더에서 Upload를 누르고 Part3 House Price.csv를 선택합니다. 목록에 노트북과 CSV가 함께 보이는지 확인합니다.
- 같은 폴더에서는 `pd.read_csv("Part3 House Price.csv")`로 읽습니다. 파일 이름의 대소문자와 공백도 동일하게 입력하세요. 다른 폴더에 두었다면 자신의 파일 위치에 맞게 경로를 바꾸세요.
- 필요한 라이브러리는 pandas, numpy, scikit-learn입니다.
- 노트북을 중간부터 실행하면 변수나 변경된 열 이름이 없다는 오류가 날 수 있습니다. 재실행할 때는 커널을 다시 시작하고 위에서부터 모두 실행하세요.
- 행 제거 결과 0행은 정상입니다. 원본 df는 남아 있으므로 다음 코드에서 원본을 계속 사용할 수 있습니다.
- 원 핫 인코딩 출력 가운데의 `...`는 pandas가 열을 생략해 표시한 것입니다. 데이터가 삭제된 것이 아닙니다.
- 마지막 두 실습은 코드에서 직접 만드는 학생·동아리 명단입니다. 별도의 파일은 필요 없습니다.
- 이 장은 전처리 방법을 익히는 예제이며 모든 결측치와 문자형 열을 모델에 바로 넣을 수 있도록 완전히 처리한 상태는 아닙니다.
