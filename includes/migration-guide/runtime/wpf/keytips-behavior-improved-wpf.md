---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497440"
---
### <a name="keytips-behavior-improved-in-wpf"></a>WPF의 향상된 키 팁 동작

#### <a name="details"></a>설명

Microsoft Word 및 Windows Explorer에서 동작으로 패리티를 가져오기 위해 키 팁 동작이 수정되었습니다. 키 팁 상태가 사용하도록 설정되거나 <xref:System.Windows.Input.KeyEventArgs.SystemKey>(특히 <xref:System.Windows.Input.Key> 또는 <xref:System.Windows.Input.Key.F11>)이 눌러지지 않았는지 여부를 확인하여 WPF는 키 팁 키를 적절히 처리합니다. 이제 키 팁은 마우스에 의해 열릴 경우에도 메뉴를 해제합니다.

#### <a name="suggestion"></a>제안 해결 방법

N/A

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.7.2|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
