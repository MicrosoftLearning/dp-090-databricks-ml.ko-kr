---
lab:
  title: 모델 관리
  module: Module 3 - Managing Experiments and Models
ms.openlocfilehash: 8989b8319c3fd55cda9c776b566b8a4a1c2b6d16
ms.sourcegitcommit: dd49d0d418bf18117549cc0ea1542b754ace865c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "139217562"
---
# <a name="managing-models"></a>모델 관리

Azure Databricks 모델 레지스트리는 배포를 위한 모델 등록, 모델 버전 관리 및 태그 지정 모델을 위한 강력한 도구입니다.  이 연습에서는 MLflow API뿐만 아니라 사용자 인터페이스를 통해 모델 레지스트리를 사용하는 방법을 알아봅니다. 시작하려면 대화형 클러스터를 사용하여 Azure Databricks 작업 영역에 액세스할 수 있어야 합니다. 작업 영역 및/또는 필수 클러스터가 없는 경우 아래 지침을 따르세요. 그렇지 않으면, [Databricks Notebook 보관 업로드](#Upload-the-Databricks-notebook-archive) 섹션으로 건너뛸 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

이 랩을 시작하기 전에 **Azure Databricks 시작하기** 랩을 완료하여 Azure Databricks 환경을 설정하고 필요한 데이터 및 Notebook을 가져옵니다.

## <a name="manage-models"></a>모델 관리

이 연습에서는 모델을 관리하는 방법에 대해 알아봅니다.

1. 웹 브라우저에서 Azure Databricks 작업 영역을 엽니다.

1. 클러스터가 실행되고 있지 않으면 **컴퓨팅** 페이지에서 클러스터를 선택하고 **시작** 단추를 사용하여 시작합니다.

1. Azure Databricks 작업 영역의 왼쪽에 있는 명령 모음을 사용하여 **작업 영역** 을 선택합니다. 그런 다음 **사용자** 를 선택하고 **&#9751; *your_user_name***을 선택합니다. 그런 다음 **03 - Managing Experiments and Models** 라는 폴더에서 **02 - Managing Models** Notebook을 엽니다.

1. 클러스터에 Notebook을 연결합니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

> **팁**: 첫 번째 섹션, **사용자 인터페이스를 통해 모델 관리** 의 경우, Notebook의 경계를 벗어나서 수행될 상당 수의 작업이 있으므로, 이러한 작업에 대한 지침이 있습니다.  브라우저에서 두 번째 탭을 열고 Notebook의 지침을 검토하면서 해당 탭에서 이러한 작업을 수행하는 것이 가장 쉬울 수 있습니다.

## <a name="clean-up"></a>정리

현재 Azure Databricks 작업을 완료한 경우 Azure Databricks 작업 영역의 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9632; 종료** 를 선택하여 종료합니다. 그렇지 않으면, 다음 연습을 위해 실행 상태로 둡니다.
