---
lab:
  title: MLflow를 사용하여 실험 추적
  module: Module 3 - Managing Experiments and Models
ms.openlocfilehash: 931fc6d405a591dab6f2539e590eb11ba0b8c7ba
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100288"
---
# <a name="using-mlflow-to-track-experiments"></a>MLflow를 사용하여 실험 추적

MLflow는 완전한 기능을 갖춘 모델 추적 및 레지스트리 시스템입니다.  이 연습에서는 MLflow를 사용하여 모델 학습 아티팩트, 메트릭, 매개 변수를 수집합니다.  그러면 Azure Databricks UI를 통해 또는 프로그래밍 방식으로 해당 출력을 볼 수 있습니다. 시작하려면 대화형 클러스터를 사용하여 Azure Databricks 작업 영역에 액세스할 수 있어야 합니다. 작업 영역 및/또는 필수 클러스터가 없는 경우 아래 지침을 따르세요. 그렇지 않으면, [Databricks Notebook 보관 업로드](#Upload-the-Databricks-notebook-archive) 섹션으로 건너뛸 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

이 랩을 시작하기 전에 [**Azure Databricks 시작하기**](Instructions/Labs/01a-introduction-to-azure-databricks.md) 랩을 완료하여 Azure Databricks 환경을 설정하고 필요한 데이터 및 Notebook을 가져옵니다. MLflow를 사용하려면 설정 랩에 설명된 대로 **ML Databricks 런타임** 버전으로 컴퓨팅 클러스터를 사용해야 합니다. 이 런타임에는 이미 MLflow 설치가 포함됩니다.

## <a name="use-mlflow-to-track-experiments"></a>MLflow를 사용하여 실험 추적

이 연습에서는 Azure Databricks 환경 내에서 데이터를 로드하고 조작하는 방법을 알아봅니다.

1. 웹 브라우저에서 Azure Databricks 작업 영역을 엽니다.

1. 클러스터가 실행되고 있지 않으면 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9654; 시작** 단추를 사용하여 시작합니다.

1. Azure Databricks 작업 영역의 왼쪽에 있는 명령 모음을 사용하여 **작업 영역** 을 선택합니다. 그런 다음, **사용자** 를 선택하고 **&#9751; *your_user_name***을 선택합니다. 그런 다음, **03 - 실험 및 모델 관리** 라는 폴더에서 **01 - MLflow를 사용하여 실험 추적** Notebook을 엽니다.

1. 클러스터에 Notebook을 연결합니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

> **팁**: **Databricks UI를 사용하여 실험, 실행, 실행 세부 정보 보기** 섹션에는 이러한 작업이 Notebook의 범위 외부에서 수행되므로 수행할 작업에 대한 지침이 있습니다.  브라우저에서 두 번째 탭을 열고 Notebook의 지침을 검토하는 동안 해당 탭에서 이러한 작업을 수행하는 것이 가장 쉬울 수 있습니다.

## <a name="clean-up"></a>정리

현재 Azure Databricks 작업을 완료한 경우 Azure Databricks 작업 영역의 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9632; 종료** 를 선택하여 종료합니다. 완료되지 않았다면 다음 랩을 위해 실행 상태로 둡니다.
