---
lab:
  title: Azure 기계 학습에서 모델 배포
  module: Module 4 - Integrating Azure Databricks and Azure Machine Learning
ms.openlocfilehash: 3d1af4dc5af8a66548c81e00f5d6012db1cb8f00
ms.sourcegitcommit: dd49d0d418bf18117549cc0ea1542b754ace865c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "139217556"
---
# <a name="deploying-models-in-azure-machine-learning"></a>Azure 기계 학습에서 모델 배포

기계 학습에서는 주로 애플리케이션에 예측 서비스를 제공하는 데 사용할 수 있는 모델의 학습을 수행합니다. 이 연습에서는 Azure Databricks에서 모델을 학습시킨 다음 Azure Machine Learning에서 모델을 배포해 보겠습니다.

## <a name="prerequisites"></a>사전 요구 사항

이 랩을 시작하기 전에 **Azure Databricks 시작하기** 및 **Azure Machine Learning에서 실험 실행** 랩을 완료하여 Azure Databricks 및 Azure Machine Learning 환경을 설정하세요.

## <a name="install-libraries-on-the-azure-databricks-cluster"></a>Azure Databricks 클러스터에 라이브러리 설치

실행할 Notebook은 클러스터에 설치해야 하는 특정 Python 라이브러리에 따라 달라집니다. 다음 단계에서는 이러한 종속성을 추가하는 단계를 안내합니다.

- Azure Databricks 작업 영역 내의 **클러스터** 섹션에서 클러스터를 선택합니다. 클러스터의 상태가 **실행 중** 인지 확인합니다.
- **라이브러리** 링크를 선택한 다음 **새로 설치** 를 선택합니다.
- 라이브러리 소스에서 **PyPi** 를 선택한 다음 **패키지** 텍스트 상자에서 `azureml-sdk[databricks]`를 입력하고 **설치** 를 선택합니다.
- 다음 설치 `sklearn-pandas==2.1.0`
- 다음 설치 `azureml-mlflow`

## <a name="deploy-a-model-in-azure-machine-learning"></a>Azure Machine Learning에서 모델 배포

이 연습에서는 Azure Databricks 환경 내에서 데이터를 로드하고 조작하는 방법을 알아봅니다.

1. 웹 브라우저에서 Azure Databricks 작업 영역을 엽니다.

1. 클러스터가 실행되고 있지 않으면 **컴퓨팅** 페이지에서 클러스터를 선택하고 **시작** 단추를 사용하여 시작합니다.

1. Azure Databricks 작업 영역의 왼쪽에 있는 명령 모음을 사용하여 **작업 영역** 을 선택합니다. 그런 다음 **사용자** 를 선택하고 **&#9751; *your_user_name***을 선택합니다. 그런 다음 **04 - Integrating Azure Databricks and Azure Machine Learning** 이라는 폴더에서 **2.0 Azure Machine Learning에서 모델 배포** Notebook을 엽니다.

1. 클러스터에 Notebook을 연결합니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## <a name="clean-up"></a>정리

현재 Azure Databricks 작업을 완료한 경우 Azure Databricks 작업 영역의 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9632; 종료** 를 선택하여 종료합니다.

Azure Databricks 탐색을 완료한 경우 Azure Databricks 및 Azure Machine Learning 리소스가 포함된 Azure 구독의 리소스 그룹을 삭제할 수 있습니다.
