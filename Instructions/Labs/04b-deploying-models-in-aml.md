---
lab:
    title: 'Azure Machine Learning에서 모델 배포'
    module: '모듈 4 - Azure Databricks와 Azure Machine Learning 통합'
---

# Azure Machine Learning에서 모델 배포

기계 학습에서는 주로 애플리케이션에 예측 서비스를 제공하는 데 사용할 수 있는 모델의 학습을 수행합니다. 이 연습에서는 Azure Databricks에서 모델을 학습시킨 다음 Azure Machine Learning에서 해당 모델을 배포하는 방법을 알아봅니다.

## 필수 구성 요소

이 랩을 시작하기 전에 **Azure Databricks 시작** 및 **Azure Machine Learning의 실험 실행** 랩을 완료하여 Azure Databricks 및 Azure Machine Learning 환경을 설정합니다.

## Azure Machine Learning에서 모델 배포

이 연습에서는 Azure Databricks 환경 내에서 데이터를 로드하고 조작하는 방법을 알아봅니다.

1. 웹 브라우저에서 Azure Databricks 작업 영역을 엽니다.

1. 클러스터가 실행되고 있지 않으면 **컴퓨팅** 페이지에서 클러스터를 선택한 후 **&#9654; 시작** 단추를 사용하여 클러스터를 시작합니다.

1. Azure Databricks 작업 영역 왼쪽의 명령 모음을 사용하여 **작업 영역**을 선택합니다. 그런 다음 **사용자**, **&#9751; *your_user_name***을 차례로 선택합니다. 그리고 나서 **04 - Azure Databricks와 Azure Machine Learning 통합** 폴더에서 **2.0 Deploying Models in Azure Machine Learning** Notebook을 엽니다.

1. 클러스터에 해당 Notebook을 연결합니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## 정리

이 연습의 Azure Databricks 작업이 끝나면 Azure Databricks 작엽 영역의 **컴퓨팅** 페이지에서 클러스터를 선택한 다음 **&#9632; 종료**를 선택하여 클러스터를 종료합니다.

Azure Databricks 살펴보기를 완료했으면 Azure 구독에서 Azure Databricks 및 Azure Machine Learning 리소스가 포함된 리소스 그룹을 삭제할 수 있습니다.
