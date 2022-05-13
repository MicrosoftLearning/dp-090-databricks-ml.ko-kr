---
lab:
  title: Azure Databricks에서 데이터 사용
  module: Module 1 - Introduction to Azure Databricks
ms.openlocfilehash: bfcfa2b977cac7df5284ffbced8fa94c516f7829
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100286"
---
# <a name="working-with-data-in-azure-databricks"></a>Azure Databricks에서 데이터 사용

DBFS를 사용하여 데이터를 로드하고 Spark 데이터 프레임을 사용하여 조작하는 방법을 알아봅니다.
DBFS(Databricks File System)는 Databricks 작업 영역에 탑재되고 Databricks 클러스터에서 사용할 수 있는 분산 파일 시스템입니다.
데이터 프레임은 대량의 데이터를 처리할 수 있는 분산된 데이터 컬렉션입니다.

## <a name="prerequisites"></a>사전 요구 사항

이 랩을 시작하기 전에 **Azure Databricks 시작하기** 랩을 완료하여 Azure Databricks 환경을 설정하고 필요한 데이터 및 Notebook을 가져옵니다.

## <a name="work-with-data-in-azure-databricks"></a>Azure Databricks에서 데이터로 작업

이 연습에서는 Azure Databricks 환경 내에서 데이터를 로드하고 조작하는 방법을 알아봅니다.

1. 웹 브라우저에서 Azure Databricks 작업 영역을 엽니다.

1. 클러스터가 실행되고 있지 않으면 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9654; 시작** 단추를 사용하여 시작합니다.

1. Azure Databricks 작업 영역의 왼쪽에 있는 명령 모음을 사용하여 **작업 영역** 을 선택합니다. 그런 다음, **사용자** 를 선택하고 **&#9751; *your_user_name***을 선택합니다. 그런 다음, **01 - Azure Databricks 소개** 라는 폴더에서 **Azure Databricks에서 데이터 작업** Notebook을 엽니다.

1. 클러스터에 Notebook을 연결합니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## <a name="clean-up"></a>정리

현재 Azure Databricks 작업을 완료한 경우 Azure Databricks 작업 영역의 **컴퓨팅** 페이지에서 클러스터를 선택하고 **&#9632; 종료** 를 선택하여 종료합니다. 완료되지 않았다면 다음 랩을 위해 실행 상태로 둡니다.
