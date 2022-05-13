---
lab:
  title: Machine Learning을 위한 데이터 준비
  module: Module 2 - Training and Evaluating Machine Learning Models
ms.openlocfilehash: c779c63d3b34c05606a93671ba800fd848bed439
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100285"
---
# <a name="preparing-data-for-machine-learning"></a>Machine Learning을 위한 데이터 준비

기계 학습에서는 주로 애플리케이션에 예측 서비스를 제공하는 데 사용할 수 있는 모델의 학습을 수행합니다. 이 연습에서는 Azure Databricks를 사용하여 기계 학습을 위해 학습 데이터를 준비하는 방법을 알아봅니다.

## <a name="prerequisites"></a>사전 요구 사항

이 랩을 시작하기 전에 **Azure Databricks 시작하기** 랩을 완료하여 Azure Databricks 환경을 설정하고 필요한 데이터 및 Notebook을 가져옵니다.

## <a name="prepare-data-for-machine-learning"></a>기계 학습에서 사용할 데이터 준비

이 연습에서는 Azure Databricks 환경 내에서 데이터를 로드하고 조작하는 방법을 알아봅니다.

1. 웹 브라우저에서 Azure Databricks 작업 영역을 엽니다.

1. 클러스터가 실행되고 있지 않으면 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9654; 시작** 단추를 사용하여 시작합니다.

1. Azure Databricks 작업 영역의 왼쪽에 있는 명령 모음을 사용하여 **작업 영역** 을 선택합니다. 그런 다음, **사용자** 를 선택하고 **&#9751; *your_user_name***을 선택합니다. 그런 다음, **02 - 기계 학습 모델 학습 및 평가** 라는 폴더에서 **1.0 기능화** Notebook을 엽니다.

1. 클러스터에 Notebook을 연결합니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## <a name="clean-up"></a>정리

현재 Azure Databricks 작업을 완료한 경우 Azure Databricks 작업 영역의 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9632; 종료** 를 선택하여 종료합니다. 완료되지 않았다면 다음 랩을 위해 실행 상태로 둡니다.
