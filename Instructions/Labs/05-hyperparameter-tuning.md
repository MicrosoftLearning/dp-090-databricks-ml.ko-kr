---
lab:
  title: Azure Databricks를 사용한 하이퍼 매개 변수 튜닝
  module: Optional exercise
ms.openlocfilehash: 9e306580175e11fdeca127b2a7fc6e2a7ed1de0f
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100320"
---
# <a name="set-up-for-hyperparameter-tuning"></a>하이퍼 매개 변수 튜닝 설정

시작하려면 대화형 클러스터를 사용하여 Azure Databricks 작업 영역에 액세스할 수 있어야 합니다. 작업 영역 및/또는 필수 클러스터가 없는 경우 아래 지침을 따르세요. 그렇지 않으면 아래 **데이터 업로드** 섹션으로 건너뛸 수 있습니다. 두 가지 연습을 완료하려면 **두 개의 다른 데이터 세트** 를 업로드해야 합니다.

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
   - **클러스터 모드**: 단일 노드
   - **풀**: 없음
   - **Databricks 런타임 버전**: *사용 가능한 최신 런타임 버전의 **ML** 버전을 선택합니다. 선택한 버전은 다음과 같아야 합니다.*
      - GPU를 사용하지 **않음**
      - Scala > **2.11** 을 포함함
      - Spark > **3.0** 을 포함함
   - **다음 이후 종료됩니다**. 120분 간 비활성
   - **노드 형식**: Standard_DS3_v2

1. 클러스터가 만들어질 때까지 기다립니다. 몇 분 정도 걸릴 수 있습니다. 클러스터가 자동으로 시작되고, 결국 클러스터 이름 옆에 있는 회전 보류 중 표시기가 단색 녹색 원으로 변경되어 실행 중 상태를 나타냅니다. 

### <a name="upload-dataset-exercise-1"></a>데이터 세트 업로드 연습 1

1. `https://github.com/MicrosoftDocs/ml-basics/blob/master/challenges/data/real_estate.csv`를 컴퓨터에 다운로드하여, 아무 폴더에나 **real_estate.csv** 로 저장합니다.

1. Databricks 작업 영역의 **데이터** 페이지에서 **테이블 만들기** 옵션을 선택합니다.

1. **파일** 영역에서 **찾아보기** 를 선택한 다음, 다운로드한 **real_estate.csv** 파일을 찾습니다.

1. 파일이 작업 영역에 업로드되면 **UI를 사용하여 테이블 만들기** 를 선택합니다. 그런 다음, 클러스터를 선택하고 **테이블 미리 보기** 를 선택합니다.

1. 다음 테이블 특성을 지정한 다음, **테이블 만들기** 를 선택합니다.

    - **테이블 이름**: real_estate
    - **데이터베이스에서 만들기**: 기본값
    - **파일 형식**: CSV
    - **열 구분 기호**: ,(쉼표)
    - **첫 번째 행이 머리글임**: 선택됨
    - **유추 스키마**: 선택됨
    - **여러 줄**: 선택 취소됨

1. 테이블을 만든 후 작업 영역에서 확인합니다.

### <a name="upload-dataset-exercise-2"></a>데이터 세트 업로드 연습 2

1. `https://github.com/MicrosoftDocs/ml-basics/blob/master/challenges/data/wine.csv`를 컴퓨터에 다운로드하여, 아무 폴더에나 **wine.csv** 로 저장합니다.

1. Databricks 작업 영역의 **데이터** 페이지에서 **테이블 만들기** 옵션을 선택합니다.

1. **파일** 영역에서 **찾아보기** 를 선택한 다음, 다운로드한 **wine.csv** 파일을 찾습니다.

1. 파일이 작업 영역에 업로드되면 **UI를 사용하여 테이블 만들기** 를 선택합니다. 그런 다음, 클러스터를 선택하고 **테이블 미리 보기** 를 선택합니다.

1. 다음 테이블 특성을 지정한 다음, **테이블 만들기** 를 선택합니다.

    - **테이블 이름**: wine
    - **데이터베이스에서 만들기**: 기본값
    - **파일 형식**: CSV
    - **열 구분 기호**: ,(쉼표)
    - **첫 번째 행이 머리글임**: 선택됨
    - **유추 스키마**: 선택됨
    - **여러 줄**: 선택 취소됨

1. 테이블을 만든 후 작업 영역에서 확인합니다.

### <a name="import-databricks-notebooks"></a>Databricks Notebooks 가져오기

1. Azure Databricks 작업 영역의 왼쪽에 있는 명령 모음을 사용하여 **작업 영역** 을 선택합니다. 그런 다음, **사용자** 를 선택하고 **&#9751; *your_user_name***을 선택합니다.

1. 표시되는 블레이드에서 이름 옆에 있는 아래쪽을 가리키는 펼침 단추(**v**)를 선택하고 **가져오기** 를 선택합니다.

1. **Notebooks 가져오기** 대화 상자에서 다음 URL에서 Notebook 보관 파일을 가져와서 보관 파일 이름의 폴더가 생성되어 두 개의 Notebook을 포함하는지 확인합니다.
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/blob/master/05%20-%20Hyperparameter%20Tuning.dbc`

## <a name="explore-automated-mlflow-hyperparameter-tuning"></a>자동화된 MLflow 하이퍼 매개 변수 튜닝 살펴보기

이 연습에서는 하이퍼 매개 변수 튜닝에 자동화된 MLflow를 사용하는 방법을 알아봅니다.

1. 작업 영역의 **05 - 하이퍼 매개 변수 튜닝** 폴더에서 **1.0 자동화된 MLflow 하이퍼 매개 변수 튜닝** Notebook을 엽니다.

1. 왼쪽 위 드롭다운 메뉴에서 클러스터를 선택하여 해당 클러스터에 Notebook을 연결합니다. (또는 연결되지 않은 Notebook에서 첫 번째 셀을 실행할 때 클러스터를 연결하라는 메시지가 표시됩니다.)

1. 그런 다음, 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## <a name="explore-hyperopt-for-hyperparameter-tuning"></a>하이퍼 매개 변수 튜닝을 위한 Hyperopt 살펴보기

이 연습에서는 하이퍼 매개 변수 튜닝에 자동화된 MLflow를 사용하는 방법을 알아봅니다.

1. 작업 영역의 **05 - 하이퍼 매개 변수 튜닝** 폴더에서 **2.0 자동화된 MLflow 하이퍼 매개 변수 튜닝** Notebook을 엽니다.

1. 왼쪽 위 드롭다운 메뉴에서 클러스터를 선택하여 해당 클러스터에 Notebook을 연결합니다. (또는 연결되지 않은 Notebook에서 첫 번째 셀을 실행할 때 클러스터를 연결하라는 메시지가 표시됩니다.)

1. 그런 다음, 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## <a name="clean-up"></a>정리

현재 Azure Databricks 작업을 완료한 경우 Azure Databricks 작업 영역의 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9632; 종료** 를 선택하여 종료합니다. 완료되지 않았다면 다음 랩을 위해 실행 상태로 둡니다.
