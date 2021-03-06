---
ms.openlocfilehash: 5a96b40e5e0df6a47415acecab410444a713632b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497935"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>ETW EventListeners는 명시적 키워드를 사용하는 공급자의 이벤트를 캡처하지 않습니다(예: TPL 공급자).

#### <a name="details"></a>설명

빈 키워드 마스크가 있는 ETW EventListeners는 명시적 키워드를 사용하는 공급자의 이벤트를 제대로 캡처하지 않습니다. .NET Framework 4.5에서 TPL 공급자는 명시적 키워드를 제공하기 시작했고 이 문제를 트리거했습니다. .NET Framework 4.6에서 더 이상 이 문제가 발생하지 않도록 EventListeners 업데이트되었습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 문제를 해결하려면 <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)>에 대한 호출을 사용할 &quot;키워드&quot; 마스크를 명시적으로 지정하는 EnableEvents 오버로드 호출로 대체합니다(<code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>). 또한 이 문제는 .NET Framework 4.6에서 해결되었으며 .NET Framework의 해당 버전으로 업그레이드하면 해결될 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`

-->
