---
title: ICorDebugMergedAssemblyRecord::GetIndex 메서드
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: b13e589e32b3317b567a4a89a5b48fc1299a1a84
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206946"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a>ICorDebugMergedAssemblyRecord::GetIndex 메서드
어셈블리의 접두사 인덱스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pIndex`  
 [out] 접두사 인덱스에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 접두사 인덱스는 병합된 메타데이터 형식 이름에서 이름 충돌을 방지하는 데 사용됩니다.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugMergedAssemblyRecord 인터페이스](icordebugmergedassemblyrecord-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
