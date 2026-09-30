# Chapter 6 · 정규화및표준화

[교재 코드 실행 영상](https://youtu.be/1R3FoQRIrJE) · [개념 강의](https://youtu.be/RxORL2QFJSo) · [전체 실습 목록](../README.md)

노트북: [CH06_실습.ipynb](CH06_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 118쪽 · 시작 안내](https://www.youtube.com/watch?v=1R3FoQRIrJE&t=0s)
- [00:12 · 교재 119쪽 · 데이터 파일 업로드](https://www.youtube.com/watch?v=1R3FoQRIrJE&t=12s)
- [00:33 · 교재 119–120쪽 · MinMaxScaler 정규화](https://www.youtube.com/watch?v=1R3FoQRIrJE&t=33s)
- [01:29 · 교재 121쪽 · 정규화 전후 분포 비교](https://www.youtube.com/watch?v=1R3FoQRIrJE&t=89s)
- [02:19 · 교재 122쪽 · StandardScaler 표준화](https://www.youtube.com/watch?v=1R3FoQRIrJE&t=139s)
- [03:09 · 교재 123–124쪽 · RobustScaler 중앙값과 IQR](https://www.youtube.com/watch?v=1R3FoQRIrJE&t=189s)
- [04:02 · 교재 125–126쪽 · 네 가지 분포 한눈에 비교](https://www.youtube.com/watch?v=1R3FoQRIrJE&t=242s)

## 실행 안내

# CHAPTER 06 실습 자료

1. 압축을 풀어 CH06_실습.ipynb와 Part3 House Price.csv를 같은 폴더에 둡니다.
2. 아나콘다의 Jupyter Notebook으로 노트북을 엽니다.
3. 새 커널에서 위에서부터 순서대로 실행합니다. 셀 실행은 Ctrl+Enter 또는 Shift+Enter입니다.

CSV는 교재 제공 원본과 같은 1460행·81열의 주택 가격 데이터입니다. 다른 폴더에 두었다면 pd.read_csv 안의 경로를 본인의 파일 위치에 맞춰 바꾸세요. 파일 이름의 공백도 동일해야 합니다.

첫 번째와 세 번째 실습에서 rename을 실행해 GrLivArea를 LivingArea로 바꿉니다. 네 번째와 다섯 번째는 CSV를 새로 읽고 원래 이름인 GrLivArea를 사용합니다. 두 이름은 같은 주택 면적 열입니다. 두 번째 그래프는 첫 번째 실습의 변환 결과를 사용하므로 순서를 지켜 실행하세요.

필요 패키지는 pandas, scikit-learn, seaborn, matplotlib입니다. 실행 결과도 저장되어 있어 영상과 비교할 수 있습니다. 결과 숫자를 코드 주석으로 붙이지 않았습니다.

교재 설명 주석 44개를 원문 그대로 포함한 수정본입니다. 첫 번째와 세 번째의 주석 처리된 rename 예시는 그대로 두고 바로 아래 줄에서 실행합니다. 네 번째는 원래 열 이름을 쓰므로 rename 주석을 해제하지 마세요. 마지막 예제의 주석에 적힌 LivingArea_MMS/SS는 교재 원문이며, 실제 코드의 열 이름은 GrLivArea_MMS/SS입니다.
