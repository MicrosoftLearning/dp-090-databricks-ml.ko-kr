---
lab:
  title: Azure Databricks를 사용한 분산 딥 러닝
  module: Optional exercise
ms.openlocfilehash: aa5c957a37af811c4ae34da317ace00b6ed235ce
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100321"
---
# <a name="set-up-for-distributed-deep-learning"></a>분산 딥 러닝 설정

시작하려면 대화형 **표준** 클러스터를 사용하여 Azure Databricks 작업 영역에 액세스할 수 있어야 합니다. 작업 영역 및/또는 필수 클러스터가 없는 경우 아래 지침을 따르세요.

## <a name="create-azure-databricks-resources"></a>Azure Databricks 리소스 만들기

Azure Databricks를 사용하려면 먼저 Azure 구독에 Azure Databricks 작업 영역을 배포하고 Notebook 및 코드를 실행할 클러스터를 만들어야 합니다. 그런 다음, 데이터 및 Notebook을 업로드하여 작업 영역에서 실험할 수 있습니다.

### <a name="deploy-an-azure-databricks-workspace"></a>Azure Databricks 작업 영역 배포

1. [Azure Portal](https://portal.azure.com)에서 다음 설정을 지정하여 새 **Azure Databricks** 리소스를 만듭니다.
   - **구독**: 작업 영역을 배포할 Azure 구독을 선택합니다.
   - **리소스 그룹**: 새 리소스 그룹을 만듭니다.
   - **작업 영역 이름**: 작업 영역의 이름을 제공합니다.
   - **지역**: 배포할 가까운 위치를 선택합니다. Azure Databricks에서 지원되는 지역 목록은 [지역별 사용 가능한 Azure 서비스](https://azure.microsoft.com/regions/services/)를 참조하세요.
   - **가격 책정 계층**: 표준

1. 작업 영역이 생성될 때까지 기다립니다. 작업 영역을 만드는 데 몇 분이 걸립니다. 작업 영역을 만드는 동안 포털의 오른쪽에 Azure Databricks에 대한 배포 제출 타일이 표시됩니다. 타일을 보려면 대시보드에서 오른쪽으로 스크롤해야 할 수도 있습니다. 화면 위쪽에 진행률 표시줄이 표시되기도 합니다. 두 영역에서 진행 상태를 볼 수 있습니다.

### <a name="create-a-cluster"></a>클러스터 생성

1. Azure Databricks 작업 영역 리소스가 만들어지면 포털에서 해당 리소스로 이동하여 **작업 영역 시작** 을 선택하여 새 탭에서 Databricks 작업 영역을 열고 메시지가 표시되면 로그인합니다.

1. Databricks 작업 영역의 왼쪽 메뉴에서 **컴퓨팅** 을 선택한 다음, **+ 클러스터 만들기** 를 선택하여 다음 구성으로 새 클러스터를 추가합니다.
   - **이름**: 고유한 이름을 입력합니다.
   - **클러스터 모드**: 표준
   - **풀**: 없음
   - **Databricks 런타임 버전**: 사용 가능한 최신 런타임 버전의 **ML** 버전을 선택합니다. 선택한 버전은 다음과 같아야 합니다.
      - 이 연습에서는 CPU 및 GPU 클러스터를 모두 사용할 수 있습니다. CPU는 GPU보다 테스트 비용이 저렴합니다.
      - Scala > **2.11** 을 포함함
      - Spark > **3.0** 을 포함함
   - **다음 이후 종료됩니다**. 120분 간 비활성
   - **노드 형식**: Standard_DS3_v2

1. 클러스터가 만들어질 때까지 기다립니다. 몇 분 정도 걸릴 수 있습니다. 클러스터가 자동으로 시작되고, 결국 클러스터 이름 옆에 있는 회전 보류 중 표시기가 단색 녹색 원으로 변경되어 실행 중 상태를 나타냅니다. 

### <a name="import-databricks-notebooks"></a>Databricks Notebooks 가져오기

1. Azure Databricks 작업 영역의 왼쪽에 있는 명령 모음을 사용하여 **작업 영역** 을 선택합니다. 그런 다음, **사용자** 를 선택하고 **&#9751; *your_user_name***을 선택합니다.

1. 표시되는 블레이드에서 이름 옆에 있는 아래쪽을 가리키는 펼침 단추(**v**)를 선택하고 **가져오기** 를 선택합니다.

1. **Notebooks 가져오기** 대화 상자에서 다음 URL에서 Notebook 보관 파일을 가져와서 보관 파일 이름의 폴더가 생성되어 두 개의 Notebook을 포함하는지 확인합니다.
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/blob/master/06%20-%20Distributed%20Deep%20Learning.dbc`

## <a name="explore-distributed-deep-learning"></a>분산 딥 러닝 살펴보기

이 연습에서는 하이퍼 매개 변수 튜닝에 자동화된 MLflow를 사용하는 방법을 알아봅니다.

1. 작업 영역의 **06 - 분산 딥 러닝** 폴더에서 **1.0 분산 딥 러닝** Notebook을 엽니다.

1. 왼쪽 위 드롭다운 메뉴에서 클러스터를 선택하여 해당 클러스터에 Notebook을 연결합니다. (또는 연결되지 않은 Notebook에서 첫 번째 셀을 실행할 때 클러스터를 연결하라는 메시지가 표시됩니다.)

1. 그런 다음, 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## <a name="clean-up"></a>정리

현재 Azure Databricks 작업을 완료한 경우 Azure Databricks 작업 영역의 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9632; 종료** 를 선택하여 종료합니다. 완료되지 않았다면 다음 랩을 위해 실행 상태로 둡니다.
