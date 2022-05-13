---
lab:
  title: Azure Databricks 시작
  module: Module 1 - Introduction to Azure Databricks
ms.openlocfilehash: 2f80eb26cad18d2b6aee094392406d8529a6c419
ms.sourcegitcommit: dd49d0d418bf18117549cc0ea1542b754ace865c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "139217559"
---
# <a name="getting-started-with-azure-databricks"></a>Azure Databricks 시작

Azure DataBricks는 빠르고 쉽게 사용 가능한 공동 작업 방식의 Spark 기반 분석 서비스입니다. 빅 데이터 분석, 인공 지능, 고성능 데이터 레이크, 대화형 데이터 과학, 기계 학습, 협업을 가속하는 데 사용됩니다.
Azure Databricks 환경 및 해당 환경의 주요 토픽인 작업 영역, 클러스터, Notebook을 검색합니다.

시작하려면 대화형 클러스터를 사용하여 Azure Databricks 작업 영역에 액세스할 수 있어야 합니다. 작업 영역 및/또는 필수 클러스터가 없는 경우 아래 지침을 따르세요. 그렇지 않으면 아래 **데이터 업로드** 섹션으로 건너뛸 수 있습니다.

## <a name="create-azure-databricks-resources"></a>Azure Databricks 리소스 만들기

Azure Databricks를 사용하려면 먼저 Azure 구독에 Azure Databricks 작업 영역을 배포하고 Notebook 및 코드를 실행할 클러스터를 만들어야 합니다. 그런 다음 작업 영역에서 실험할 데이터 및 Notebook을 업로드할 수 있습니다.

### <a name="deploy-an-azure-databricks-workspace"></a>Azure Databricks 작업 영역 배포

1. Azure Portal ‘ https://portal.azure.com ’에서 새 **Azure Databricks** 리소스를 만들어 다음 설정을 지정합니다.
   - **구독**: 작업 영역을 배포할 Azure 구독을 선택합니다.
   - **리소스 그룹**: 새 리소스 그룹을 만듭니다.
   - **작업 영역 이름**: 작업 영역의 이름을 제공합니다.
   - **지역**: 배포할 가까운 위치를 선택합니다. Azure Databricks에서 지원되는 지역 목록은 [지역별 사용 가능한 Azure 서비스](https://azure.microsoft.com/regions/services/)를 참조하세요.
   - **가격 책정 계층**: 표준

1. 작업 영역이 생성될 때까지 기다립니다. 작업 영역을 만드는 데 몇 분이 걸립니다. 작업 영역을 만드는 동안 포털의 오른쪽에 Azure Databricks에 대한 배포 제출 타일이 표시됩니다. 타일을 보려면 대시보드에서 오른쪽으로 스크롤해야 할 수도 있습니다. 화면 위쪽에 진행률 표시줄이 표시되기도 합니다. 두 영역에서 진행 상태를 볼 수 있습니다.

### <a name="create-a-cluster"></a>클러스터 생성

1. Azure Databricks 작업 영역 리소스가 만들어지면 포털에서 해당 리소스로 이동하여 **작업 영역 시작** 을 선택하여 새 탭에서 Databricks 작업 영역을 열고 메시지가 표시되면 로그인합니다.

1. Databricks 작업 영역의 왼쪽 메뉴에서 **컴퓨팅** 을 선택한 다음 **+ 클러스터 만들기** 를 선택하여 다음 구성으로 새 클러스터를 추가합니다.
   - **이름**: 고유한 이름을 입력합니다.
   - **클러스터 모드**: 단일 노드
   - **Databricks 런타임 버전**: 사용 가능한 최신 런타임 버전의 **ML** 에디션을 선택합니다. 선택한 버전은 다음과 같아야 합니다.
      - GPU를 사용하지 **않음**
      - Scala > **2.11** 을 포함함
      - Spark > **3.0** 을 포함함
   - **다음 이후 종료**: 120분 간 비활성
   - **노드 유형**: Standard_DS3_v2

1. 클러스터가 만들어질 때까지 기다립니다. 몇 분 정도 걸릴 수 있습니다. 클러스터가 자동으로 시작되고, 결국 클러스터 이름 옆에 있는 회전 보류 중 표시기가 단색 녹색 원으로 변경되어 실행 중 상태를 나타냅니다. 

### <a name="upload-data"></a>데이터 업로드

1. `https://raw.githubusercontent.com/MicrosoftLearning/dp-090-databricks-ml/master/data/nyc-taxi.csv`를 컴퓨터에 다운로드하여, 아무 폴더에나 **nyc-taxi.csv** 로 저장합니다.

1. Databricks 작업 영역의 **데이터** 페이지에서 **테이블 만들기** 옵션을 선택합니다.

1. **파일** 영역에서 **찾아보기** 를 선택한 다음 다운로드한 **nyc-taxi.csv** 파일을 찾습니다.

1. 파일이 작업 영역에 업로드되면 **UI를 사용하여 테이블 만들기** 를 선택합니다. 그런 다음 클러스터를 선택하고 **테이블 미리 보기** 를 선택합니다.

1. 다음 테이블 특성을 지정합니다.

    - **테이블 이름**: nyc_taxi
    - **데이터베이스에서 만들기**: 기본값
    - **파일 형식**: CSV
    - **열 구분 기호**: ,(쉼표)
    - **첫 번째 행이 머리글임**: 선택됨
    - **유추 스키마**: 선택됨
    - **여러 줄**: 선택 취소됨

1. 각 열에 적절한 데이터 형식을 설정합니다. **passengerCount** 열을 찾습니다. 드롭다운 메뉴에서 열을 **INT** 로 설정합니다.

    - passengerCount: **INT**
    - tripDistance: **DOUBLE**
    - hour_of_day: **INT**
    - day_of_week: **INT**
    - month_num: **INT**
    - normalizeHolidayName: **STRING**
    - isPaidTimeOff: **BOOLEAN**
    - snowDepth: **DOUBLE**
    - precipTime: **DOUBLE**
    - precipDepth: **DOUBLE**
    - 온도: **DOUBLE**
    - totalAmount: **DOUBLE**

1. **테이블 만들기** 를 클릭합니다.

1. 테이블을 만든 후 작업 영역에서 봅니다.

### <a name="import-databricks-notebooks"></a>Databricks Notebooks 가져오기

1. Azure Databricks 작업 영역의 왼쪽에 있는 명령 모음을 사용하여 **작업 영역** 을 선택합니다. 그런 다음 **사용자** 를 선택하고 **&#9751; *your_user_name***을 선택합니다.

1. 표시되는 창에서 이름 옆에 있는 아래쪽을 가리키는 펼침 단추(**v**)를 선택하고 **가져오기** 를 선택합니다.

1. **Notebooks 가져오기** 대화 상자에서 다음 URL에서 Notebook 보관 파일을 가져와서 보관 파일 이름의 폴더가 생성되어 하나 이상의 Notebook을 포함하는지 확인합니다.
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/01%20-%20Introduction%20to%20Azure%20Databricks.dbc`

1. 이전 단계를 반복하여 다음 Notebook 보관 파일을 가져오면, 가져온 각 보관 파일에 대해 폴더가 생성됩니다.

   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/02%20-%20Training%20and%20Evaluating%20Machine%20Learning%20Models.dbc`
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/03%20-%20Managing%20Experiments%20and%20Models.dbc`
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/04%20-%20Integrating%20Azure%20Databricks%20and%20Azure%20Machine%20Learning.dbc`

## <a name="explore-azure-databricks"></a>Azure Databricks 탐색

이 연습에서는 Azure Databricks 환경을 검색합니다.

1. 작업 영역의 **01 - Introduction to Azure Databricks** 폴더에서 **Azure Databricks 시작하기** Notebook을 엽니다.

1. 왼쪽 위 드롭다운 메뉴에서 클러스터를 선택하여 해당 클러스터에 Notebook을 연결합니다. (또는 연결되지 않은 Notebook에서 첫 번째 셀을 실행할 때 클러스터를 연결하라는 메시지가 표시됩니다.)

1. 각 코드 셀을 실행하여 Notebook의 메모를 읽습니다.

## <a name="clean-up"></a>정리

현재 Azure Databricks 작업을 완료한 경우 Azure Databricks 작업 영역의 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9632; 종료** 를 선택하여 종료합니다. 그렇지 않으면, 다음 연습을 위해 실행 상태로 둡니다.
