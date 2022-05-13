---
title: 온라인 호스팅 지침
permalink: index.html
layout: home
ms.openlocfilehash: 8d795701e8cdc53c61c6df0d8ff245c0d8969940
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100305"
---
# <a name="content-directory"></a>콘텐츠 디렉터리

랩 연습은 아래에 나열되어 있습니다.

## <a name="labs"></a>랩

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| 모듈 | 랩 |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
