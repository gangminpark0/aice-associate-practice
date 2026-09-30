# Chapter 4 · 데이터시각화

[교재 코드 실행 영상](https://youtu.be/OcyB5_roUhg) · [개념 강의](https://youtu.be/BncYR4-SFlo) · [전체 실습 목록](../README.md)

노트북: [CH04_실습.ipynb](CH04_실습.ipynb)

저장소 첫 화면의 **Code → Download ZIP**으로 내려받아 압축을 푼 뒤, 이 폴더의 노트북을 엽니다. CSV가 있는 장은 CSV를 노트북과 같은 폴더에 유지하세요. 노트북과 데이터 파일을 하나씩 내려받을 때는 각 파일의 **Download raw file**을 사용합니다.

## 영상의 교재 페이지별 바로가기

- [00:00 · 교재 71쪽 · 시작 안내](https://www.youtube.com/watch?v=OcyB5_roUhg&t=0s)
- [00:12 · 교재 72쪽 · 데이터 파일 업로드](https://www.youtube.com/watch?v=OcyB5_roUhg&t=12s)
- [00:42 · 교재 72쪽 · 라이브러리와 데이터 준비](https://www.youtube.com/watch?v=OcyB5_roUhg&t=42s)
- [01:15 · 교재 73쪽 · 생존자와 사망자 수](https://www.youtube.com/watch?v=OcyB5_roUhg&t=75s)
- [01:49 · 교재 74쪽 · 객실 등급별 승객 수](https://www.youtube.com/watch?v=OcyB5_roUhg&t=109s)
- [02:21 · 교재 75쪽 · 승객 나이 분포](https://www.youtube.com/watch?v=OcyB5_roUhg&t=141s)
- [03:00 · 교재 76쪽 · 객실 등급별 생존율](https://www.youtube.com/watch?v=OcyB5_roUhg&t=180s)
- [03:36 · 교재 77쪽 · 성별 생존율](https://www.youtube.com/watch?v=OcyB5_roUhg&t=216s)
- [04:11 · 교재 77쪽 · 객실 등급별 요금 분포](https://www.youtube.com/watch?v=OcyB5_roUhg&t=251s)
- [04:46 · 교재 78쪽 · 나이와 요금의 산점도](https://www.youtube.com/watch?v=OcyB5_roUhg&t=286s)
- [05:19 · 교재 79쪽 · 관계와 분포를 함께 보기](https://www.youtube.com/watch?v=OcyB5_roUhg&t=319s)
- [05:46 · 교재 80쪽 · 상관관계 히트맵](https://www.youtube.com/watch?v=OcyB5_roUhg&t=346s)
- [06:38 · 교재 81쪽 · 나이에 따른 평균 요금](https://www.youtube.com/watch?v=OcyB5_roUhg&t=398s)
- [07:12 · 교재 82쪽 · 객실 등급과 성별을 함께 비교](https://www.youtube.com/watch?v=OcyB5_roUhg&t=432s)

## 실행 안내

# 데이터 시각화 실습 준비

압축파일을 풀고 모든 파일을 같은 폴더에 둡니다. 아나콘다의 Jupyter Notebook에서 CH04_실습.ipynb를 열어 위에서 아래로 실행하세요.

- **Part2 Titanic.csv**: 교재 제공 원본 데이터, 891행·12열입니다. 수정하지 않았습니다.
- **matplotlibrc**: Windows 맑은 고딕으로 한글을 표시하는 설정 파일입니다. 처음 라이브러리를 불러오기 전부터 노트북과 같은 폴더에 두세요. 이미 실행 중이라면 커널을 다시 시작한 뒤 실행합니다.
- CSV를 별도로 넣으려면 노트북이 있는 Jupyter 폴더에서 Upload를 누르고 Part2 Titanic.csv를 선택합니다. 목록에 노트북과 CSV가 함께 보이는지 확인합니다.
- 같은 폴더에서는 `pd.read_csv("Part2 Titanic.csv")`로 읽습니다. 다른 곳에 두었다면 자신의 파일 위치에 맞게 경로를 바꾸세요.
- 필요한 라이브러리는 pandas, seaborn, matplotlib입니다. 그래프에 사용되는 Age 결측치는 함수가 자동 제외하며, 파일 자체를 삭제하거나 변경하지 않습니다.
- 제공된 한글 설정은 Windows용입니다. macOS에서는 matplotlibrc의 `font.family`를 `AppleGothic`으로, 그 밖의 환경에서는 설치된 한글 글꼴 이름으로 바꾸세요.
- 교재의 figsize를 유지합니다. 영상에서는 화면에 맞게 표시 크기만 조정했으므로 개인 화면의 그래프 크기는 다를 수 있습니다.
- 막대와 선 그래프의 신뢰구간은 무작위 재표본추출로 계산되어 실행마다 조금 달라질 수 있습니다. 막대 높이와 평균값은 동일합니다.
