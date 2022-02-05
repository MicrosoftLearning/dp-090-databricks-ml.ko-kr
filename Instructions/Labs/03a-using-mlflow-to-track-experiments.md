---
lab:
    title: 'MLflow를 사용하여 실험 추적'
    module: '모듈 3 - 실험 및 모델 관리'
---

# MLflow를 사용하여 실험 추적

MLflow는 모든 기능을 갖춘 모델 추적 및 레지스트리 시스템입니다.  이 연습에서는 MLflow를 사용하여 모델 학습 아티팩트, 메트릭 및 매개 변수를 수집합니다.  그리고 나면 Azure Databricks UI를 사용하거나 프로그래밍 방식으로 해당 출력을 확인할 수 있습니다. 시작하려면 대화형 클러스터를 사용하여 Azure Databricks 작업 영역에 액세스할 수 있어야 합니다. 작업 영역 및/또는 필수 클러스터가 없는 경우 아래 지침을 따르세요. 그렇지 않으면 아래의 [Databricks Notebook 보관 파일 업로드](#Upload-the-Databricks-notebook-archive) 섹션으로 건너뛸 수 있습니다.

## 필수 구성 요소

이 랩을 시작하기 전에 [**Azure Databricks 시작**](Instructions/Labs/01a-introduction-to-azure-databricks.md) 랩을 완료하여 Azure Databricks 환경을 설정하고 필요한 데이터와 Notebook을 가져옵니다. MLflow를 사용하려면 설정 랩의 지침에 따라 **ML Databricks Runtime** 버전이 설치된 컴퓨팅 클러스터를 사용해야 합니다. 이 런타임에는 MLflow 설치가 이미 포함되어 있습니다.

## MLflow를 사용하여 실험 추적

이 연습에서는 Azure Databricks 환경 내에서 데이터를 로드하고 조작하는 방법을 알아봅니다.

1. 웹 브라우저에서 Azure Databricks 작업 영역을 엽니다.

1. 클러스터가 실행되고 있지 않으면 **컴퓨팅** 페이지에서 클러스터를 선택한 후 **&#9654; 시작** 단추를 사용하여 클러스터를 시작합니다.

1. Azure Databricks 작업 영역 왼쪽의 명령 모음을 사용하여 **작업 영역**을 선택합니다. 그런 다음 **사용자**, **&#9751; *your_user_name***을 차례로 선택합니다. 그리고 나서 **03 - 실험 및 모델 관리** 폴더에서 **01 - Using MLflow to Track Experiments** Notebook을 엽니다.

1. 클러스터에 해당 Notebook을 연결합니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

> **팁**: **Databricks UI를 사용하여 실험, 실행 및 실행 세부 정보 확인** 섹션에서 수행할 작업 관련 지침이 제공됩니다. 이러한 작업은 Notebook 외부에서 수행해야 합니다.  그러므로 Notebook의 지침을 검토하면서 브라우저에서 두 번째 탭을 열고 해당 탭에서 이러한 작업을 수행하는 방식이 가장 쉽습니다.

## 정리

이 연습의 Azure Databricks 작업이 끝나면 Azure Databricks 작엽 영역의 **컴퓨팅** 페이지에서 클러스터를 선택한 다음 **&#9632; 종료**를 선택하여 클러스터를 종료합니다. 작업이 끝나지 않았다면 다음 연습을 위해 실행 상태로 둡니다.
