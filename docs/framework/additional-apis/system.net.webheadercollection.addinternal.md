---
title: WebHeaderCollection. AddInternal 메서드 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990462"
---
# <a name="webheadercollectionaddinternal-method"></a>WebHeaderCollection. AddInternal 메서드

검사를 무시 하 고 컬렉션에 지정 된 이름과 값을 가진 새 헤더를 추가 합니다.

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> 이 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="parameters"></a>매개 변수

- `name` <xref:System.String>

  헤더의 이름입니다.

- `value` <xref:System.String>

  헤더의 값입니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
