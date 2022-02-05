---
lab:
    title: 'Azure Databricks에서 데이터 사용'
    module: '모듈 1 - Azure Databricks 소개'
---

# Azure Databricks에서 데이터 사용

이 랩에서는 DBFS를 사용하여 데이터를 로드한 다음 Spark 데이터 프레임을 사용하여 조작하는 방법을 알아봅니다.
DBFS(Databricks File System)는 Databricks 작업 영역에 탑재되며 Databricks 클러스터에서 사용할 수 있는 분산 파일 시스템입니다.
분산형 데이터 컬렉션인 데이터 프레임에서는 대량의 데이터를 처리할 수 있습니다.

## 필수 구성 요소

이 랩을 시작하기 전에 **Azure Databricks 시작** 랩을 완료하여 Azure Databricks 환경을 설정하고 필요한 데이터와 Notebook을 가져옵니다.

## Azure Databricks에서 데이터 사용

이 연습에서는 Azure Databricks 환경 내에서 데이터를 로드하고 조작하는 방법을 알아봅니다.

1. 웹 브라우저에서 Azure Databricks 작업 영역을 엽니다.

1. 클러스터가 실행되고 있지 않으면 **컴퓨팅** 페이지에서 클러스터를 선택한 후 **&#9654; 시작** 단추를 사용하여 클러스터를 시작합니다.

1. Azure Databricks 작업 영역 왼쪽의 명령 모음을 사용하여 **작업 영역**을 선택합니다. 그런 다음 **사용자**, **&#9751; *your_user_name***을 차례로 선택합니다. 그리고 나서 **01 - Azure Databricks 소개** 폴더에서 **Working with data in Azure Databricks** Notebook을 엽니다.

1. 클러스터에 해당 Notebook을 연결합니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## 정리

이 연습의 Azure Databricks 작업이 끝나면 Azure Databricks 작엽 영역의 **컴퓨팅** 페이지에서 클러스터를 선택한 다음 **&#9632; 종료**를 선택하여 클러스터를 종료합니다. 작업이 끝나지 않았다면 다음 연습을 위해 실행 상태로 둡니다.
