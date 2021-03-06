---
title: 취소 요청에 대한 콜백 등록
ms.date: 08/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: faa8dada5779f6eaee7a60e6210ec604f5fb4680
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608448"
---
# <a name="register-callbacks-for-cancellation-requests"></a>취소 요청에 대한 콜백 등록

<xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성이 true가 될 때 호출되는 대리자를 등록하는 방법을 알아봅니다. 토큰을 만든 개체에서 <xref:System.Threading.CancellationTokenSource.Cancel%2A>을 호출하면 값이 false에서 true로 변경됩니다. 이 기술은 통합된 취소 프레임워크를 기본적으로 지원하지 않는 비동기 작업을 취소하고 비동기 작업이 완료되기를 기다리고 있는 메서드의 차단을 해제하는 데 사용합니다.

> [!NOTE]
> “내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다. 이 오류는 심각하지는 않습니다. <kbd>F5</kbd> 키를 눌러 해당 지점부터 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다. 첫 번째 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 “내 코드만” 확인란의 선택을 취소하기만 하면 됩니다.

## <a name="example"></a>예제

다음 예제에서 <xref:System.Net.WebClient.CancelAsync%2A> 메서드는 취소 토큰을 통해 취소가 요청될 때 호출할 메서드로 등록됩니다.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb":::

콜백을 등록할 때 이미 취소가 요청된 경우에도 콜백 호출이 보장됩니다. 이 특별한 경우에서는 진행 중인 비동기 작업이 없는 경우 <xref:System.Net.WebClient.CancelAsync%2A> 메서드가 아무 작업도 하지 않으므로 항상 안전하게 메서드를 호출할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [관리형 스레드에서의 취소](cancellation-in-managed-threads.md)
- <xref:System.Net.WebClient.DownloadStringTaskAsync(System.String)?displayProperty=nameWithType>
