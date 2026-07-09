# 전력사용량 예측 경진대회

[![Python](https://img.shields.io/badge/python-3.10-3776AB?logo=python&logoColor=white)](https://www.python.org) [![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)

건물별 시간 단위 전력사용량을 예측했습니다. 건물마다 다른 운영 패턴과 기상·달력 변수를 함께 활용해 상위 8.7%를 기록했습니다.

## 개요

| 구분 | 내용 |
| --- | --- |
| 대회 | 2023 전력사용량 예측 AI 경진대회 |
| 기간 | 2023.07.17 – 2023.08.28 |
| 주최 / 주관 | 한국에너지공단 / 데이콘 |
| 평가지표 | SMAPE |
| 결과 | 상위 8.7% |
| 과제 | 건물별 시간 단위 전력사용량 예측 |

## 접근

- 건물 정보, 기상, 달력, 시간대별 소비 패턴을 EDA로 점검했습니다.
- `mljar-supervised` AutoML로 baseline을 빠르게 만들고 모델 계열을 비교했습니다.
- 건물마다 운영 패턴이 달라 건물 단위 Prophet 모델을 실험했습니다.
- 예측이 불안정한 구간은 요일·시간대 중앙값으로 보정했습니다.

## 저장소 구성

```text
.
├── notebooks/
│   ├── 01_analysis_preprocessing.ipynb
│   ├── 02_automl_baseline.ipynb
│   ├── 03_prophet_experiment.ipynb
│   ├── 04_original_prophet_submission.ipynb
│   └── 05_refactored_prophet_pipeline.ipynb
├── requirements.txt
└── requirements-automl.txt
```

## 공개 범위

대회 원본 데이터, 제출 파일, 모델 산출물, AutoML 결과 디렉터리는 포함하지 않았습니다. 데이터는 대회 참가자에게만 제공되어 그대로 재현하기는 어렵고, 저장소에는 접근 방식을 담은 노트북만 남겼습니다. 데이터를 `data/`에 두면 노트북을 번호 순서대로 실행할 수 있고, 필요한 패키지는 `requirements.txt`와 `requirements-automl.txt`에 정리했습니다.

## 링크

- [대회 페이지](https://dacon.io/competitions/official/236125/overview/description)
- [최종 리더보드](https://dacon.io/competitions/official/236125/leaderboard)

## 라이선스

Apache License 2.0. 자세한 내용은 [LICENSE](LICENSE)에 있습니다.
