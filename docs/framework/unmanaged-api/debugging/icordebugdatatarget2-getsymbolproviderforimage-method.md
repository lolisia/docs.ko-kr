---
title: ICorDebugDataTarget2::GetSymbolProviderForImage 메서드
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 7800630be0ed9afb321d607046be308088781388
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976449"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a>ICorDebugDataTarget2::GetSymbolProviderForImage 메서드
모듈의 시스템 공급자를 해당 모듈의 기본 주소에서 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `imageBaseAddress`  
 진행 모듈의 기준 주소를 나타내는 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) 값입니다.  
  
 `ppSymProvider`  
 제한이 [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugDataTarget2 인터페이스](icordebugdatatarget2-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
